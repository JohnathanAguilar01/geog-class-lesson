# 🌊 geog-class-lesson

**Cloud-Native Sea Surface Temperature (SST) Analysis with Python**

This repository contains a complete, classroom-ready GIS / Remote Sensing lesson that demonstrates how to:

* Authenticate with NASA Earthdata
* Stream satellite data directly from the cloud
* Process and clip gridded SST data using `xarray`
* Perform temporal resampling (daily → weekly averages)
* Generate maps, time series plots, and animated GIFs
* Save reproducible NetCDF outputs

The workflow is designed for undergraduate Geography, GIS, Environmental Science, or Data Science courses.

---

# 📚 Learning Objectives

By the end of this lesson, students will be able to:

* Understand cloud-native Earth observation workflows
* Use `earthaccess` to search and retrieve NASA datasets
* Work with multidimensional geospatial data using `xarray`
* Apply coordinate reference systems (CRS) correctly
* Clip raster datasets to vector study areas
* Compute summary statistics from gridded time series data
* Resample temporal data (daily → weekly → monthly)
* Create animated SST visualizations

---

# 🛰 Dataset Used

This lesson uses Level-4 Sea Surface Temperature (SST) products from NASA Earthdata.

Primary example:

* **OSTIA-UKMO-L4-GLOB-v2.0**

  * ~5 km resolution
  * Daily global coverage
  * Gap-free blended product

The workflow can easily be adapted to:

* `MUR-JPL-L4-GLOB-v4.1` (~1 km resolution)
* `CMC0.2deg-CMC-L4-GLOB-v3.0`

---

# 🗺 Study Area

Caribbean / Seaflower Marine Protected Area

The lesson demonstrates:

* Loading shapefiles with `geopandas`
* Checking CRS (EPSG:4326)
* Reprojecting to Web Mercator (EPSG:3857)
* Overlaying basemaps with `contextily`

---

# 🔧 Technologies & Libraries

* `numpy`
* `xarray`
* `rioxarray`
* `geopandas`
* `matplotlib`
* `matplotlib.animation`
* `earthaccess`
* `contextily`
* `h5netcdf`
* `IPython.display`

This workflow follows a **cloud-native remote sensing paradigm**, meaning:

> We stream only the required spatial and temporal subset of data rather than downloading full global files.

---

# 🗂 Repository Structure

```
geog-class-lesson/
│
├── notebook.ipynb              # Main lesson notebook
├── requirements.txt            # Python dependencies
├── outputs/                    # Saved NetCDF + GIF outputs
├── Shape_Files/                # Study area shapefile
└── README.md
```

---

Perfect — here’s a clean replacement **Setup** section you can drop into your `README.md` that directs users to the PDF instructions.

---

# 🚀 Setup Instructions

To ensure a smooth and consistent setup, **please follow the step-by-step guide provided in:**

```
geog_lesson_instructions.pdf
```

This document includes:

* NASA Earthdata account setup
* Google Collab setup

⚠️ **Important:**
Do not skip the PDF instructions — the notebook assumes the environment has been configured exactly as described there.

---

# 🔐 NASA Earthdata Account Required

You must create a free NASA Earthdata account:

👉 [https://urs.earthdata.nasa.gov/](https://urs.earthdata.nasa.gov/)

The notebook uses:

```python
ea.login(persist=False)
```

You will be prompted for credentials when running the lesson.

---

# 📈 Workflow Overview

1. Install dependencies
2. Import geospatial libraries
3. Load shapefile (Caribbean study area)
4. Authenticate with NASA Earthdata
5. Search SST granules by:

   * Dataset short name
   * Bounding box
   * Date range
6. Open cloud-hosted granules with `xarray`
7. Convert Kelvin → Celsius
8. Assign CRS and clip to study area
9. Save processed data to NetCDF
10. Reload for reproducibility
11. Resample to weekly averages
12. Generate:

* SST map with basemap
* Time series plot
* Animated GIF timelapse

---

# 🎓 Pedagogical Focus

This lesson emphasizes:

* Reproducible geospatial workflows
* Proper CRS handling
* Cloud-native data access
* Temporal aggregation strategies
* Scientific visualization best practices

It is structured so each cell includes instructional markdown explaining:

* What the code does
* Why it is done
* The underlying geospatial/data science concept

---

# 🧠 Key Concepts Covered

* Level-4 satellite products
* Granules in NASA CMR
* Lazy loading in `xarray`
* Spatial clipping with `rioxarray`
* Temporal resampling (`resample`)
* Diverging vs sequential colormaps
* Web Mercator vs WGS84 projections
* NetCDF as a scientific data format

---

# 🔁 Reproducibility

Processed SST data is saved locally as:

```
outputs/SST_Data.nc
```

This allows:

* Skipping cloud retrieval on reruns
* Faster downstream analysis
* Clear workflow checkpoints

---

# 🌍 Why This Matters

Modern Earth observation research is shifting toward:

* Cloud-native data access
* Scalable workflows
* Programmatic geospatial analysis
* Reproducible computational notebooks

This lesson gives students hands-on experience with real-world remote sensing pipelines used in research and operational oceanography.

---

# 👨‍🏫 Instructor Notes

This lesson works well for:

* Upper-division GIS courses
* Introductory Remote Sensing
* Environmental Data Science
* Climate Analytics modules

Estimated runtime:

* 60–90 minutes (guided)
* 2–3 hours (independent lab)

---

# 📜 License

MIT License
