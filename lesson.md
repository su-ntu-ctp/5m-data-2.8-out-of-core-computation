# Lesson

## Brief

### Preparation

Create the conda environment based on the `ooc-environment.yml` file in the [environment folder](https://github.com/su-ntu-ctp/5m-data-2.1-intro-big-data-eng/tree/main/environments).

### Lesson Overview

In this lesson, we will be learning about _out of core_ dataframe and data processing. We will use `Polars`, an alternative dataframe libraries to `Pandas` for more performant and scalable data processing. We will also use `DuckDB` to query data that is too large to fit in memory.

_Out of core_ computation is a technique that allows us to process data that is **too large to fit in memory**. This is a common problem in data science and data engineering. Although Pandas is the de-facto dataframe library that is used in data science and data engineering, it is limited by the amount of memory (RAM) available on the machine as it is an _in-memory_ dataframe library. It is also less performant, as it processes data in a _single thread_, which is a bottleneck for modern computers that have multiple cores.

Polars is an alternative dataframe library that is more performant and scalable than Pandas. It's designed to be fast, using **Arrow** arrays as its foundation, and it can leverage _multi-threading_ for various operations. This makes it particularly useful for large datasets. Polars can process data in chunks. Instead of loading the entire dataset into memory, it reads and processes data in manageable chunks. This means that even if the dataset is larger than available memory, Polars can still handle it by sequentially processing each chunk.

However, being a newer library, Polars might not have all the features that Pandas provides, but it is rapidly improving.

---

## Part 1 - Out-of-core Computation and Data Frames

We will be using the `out_of_core.ipynb` notebook throughout this lesson.

> Open the notebook in VSCode by double clicking on the file. Then select `ooc` conda environment for the kernel.
>
> Follow on with the lesson in the notebook.
