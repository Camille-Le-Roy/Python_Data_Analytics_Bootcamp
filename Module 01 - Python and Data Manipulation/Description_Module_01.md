# Python and Data Manipulation Module

This repository serves as a centralized hub for the foundational modules of the curriculum. The modules transition from core object-oriented program design to performance optimization, geospatial analysis, and interactive data storytelling.

---

## Week 1: Object-Oriented Data Pipeline Architecture

### Phase 1: Base Architecture and Mixins
Builds the foundational structural layer of the pipeline using object-oriented principles:
*   **Abstraction (DataComponent):** An abstract base class enforcing an explicit interface via a mandatory `.execute()` method.
*   **Mixins:** Decoupled, reusable utility modules including `ValidatorMixin` for file and column structural safeguards, and `LoggerMixin` for console-based state tracking.

### Phase 2: Ingestion and Transformation
Handles data input/output operations and data sanitation:
*   **DataLoader:** Inherits from `DataComponent` and utilizes encapsulated private attributes (`__file_path`) to securely read data sources into Pandas DataFrames.
*   **DataCleaner:** A transformation engine that manages missing values, type casting, and exposes clean dataset metadata using Python `@property` decorators.

### Phase 3: Analytics and Orchestration
Processes data insights and manages end-to-end execution:
*   **DataAnalyst:** Demonstrates polymorphism by exposing flexible diagnostic tools, generating both structural console summaries and static visualizations via Matplotlib and Seaborn.
*   **Pipeline Orchestration:** A centralized runtime execution script that instantiates components and runs the full pipeline flow.

### Deliverables
A Jupyter Notebook (`.ipynb`) containing complete class definitions, a technical markdown report evaluating architectural trade-offs (Inheritance vs. Mixins), and a live proof of concept using a real-world dataset.

---

## Week 2: Code Profiling, Optimization, and Scientific Computing

### Phase 1: Profiling and Diagnosis
Establishes performance baselines by diagnosing an inefficient, loop-heavy codebase processing one million records:
*   **CPU Profiling:** Utilizing `cProfile` to pinpoint operational bottlenecks.
*   **Memory Profiling:** Applying `memory_profiler` to identify critical RAM consumption peaks.

### Phase 2: Custom Performance Decorators
Development of a reusable performance monitoring tool:
*   **Performance Monitor:** Implementation of a custom `@monitor_rendimiento` decorator wrapped around processing functions to capture exact execution duration and memory deltas.

### Phase 3: Refactoring and Scientific Modeling
Replacing inefficient loops with high-performance mathematical libraries:
*   **NumPy Optimization:** Implementing vectorization via broadcasting and replacing conditional statements with boolean masks (fancy indexing).
*   **Statistical Modeling:** Performing loss minimization via `scipy.optimize` alongside ordinary least squares (OLS) linear regressions with `statsmodels`.

### Deliverables
A single notebook containing the original inefficient script, the functional monitoring decorator, the optimized NumPy/SciPy code, and a comparative report detailing performance metrics before and after refactoring.

---

## Week 3: Temporal and Geospatial Data Engineering

### Phase 1: Temporal Data Engineering
Standardizing and structuring time-series components within urban mobility datasets:
*   **Standardization:** Converting raw timestamps using `pd.to_datetime` with robust error coercion.
*   **Indexing and Resampling:** Establishing chronological indices to enable weekly or monthly downsampling alongside explicit timezone localization and conversion.

### Phase 2: Geospatial Transformation
Converting standard tabular data structures into spatial vector geometries:
*   **Geometry Generation:** Mapping raw latitude and longitude coordinates into Shapely `Point` objects.
*   **Coordinate Reference Systems (CRS):** Initializing spatial boundaries under the WGS84 system (EPSG:4326) and projecting to localized systems for precise metric distance calculations.

### Phase 3: Spatial Intersection and Visualization
Merging geographic data layers to extract administrative insights:
*   **Spatial Joins:** Cross-referencing coordinates with district GeoJSON polygons via `sjoin`.
*   **Cartographic Visualization:** Mapping event intensity across administrative boundaries and pairing them with temporal trendlines.

---

## Week 4: Generative AI Strategy, Interactive Visualizations, and Storytelling

### Phase 1: Data Acquisition and AI Strategy
Sourcing datasets and designing layouts using generative intelligence:
*   **Preparation:** Acquiring the source data and executing introductory cleaning passes within a notebook environment.
*   **Prompt Engineering:** Consulting an AI model to structure optimal interactive visualization layouts, documenting the exact prompts within markdown blocks.

### Phase 2: Static and Interactive Visual Layers
Developing tiered graphical outputs to explore data correlations:
*   **Static Analytics:** Generating correlation heatmaps or joint plots with optimized palettes like Viridis using Seaborn.
*   **Interactive Dashboards:** Building declarative visualizations in Altair and scatter plots containing custom hover tooltips using Plotly.

### Phase 3: Data Storytelling and Delivery
Translating graphical patterns into actionable business recommendations:
*   **Narrative Integration:** Writing contextual conclusions below each visualization explaining detected trends and data-driven insights.
*   **Moodle Delivery Requirements:** Submission of a single, fully executable Jupyter Notebook free of runtime or dependency import errors.
