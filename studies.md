# Self Studies

**⏳ Estimated Prep Time:** 30–45 minutes

Welcome to our flipped-classroom session, where you'll review foundational concepts beforehand to maximize our time for hands-on coding and debugging. This pre-study focuses on mastering **Out-of-Core Computation** using libraries like **Polars** and **DuckDB**, ensuring you are ready to process datasets that are too large to fit into your machine's memory (RAM).

## **⚡ Your Self-Study Tasks**

Please complete the following activities before our session.

### **📝 Task 1: The "Why" of Out-of-Core Processing (10 Minutes)**

**Activity:** Read the **"Lesson Overview"** and **"Part 1 \- Out-of-core Computation and Data Frames"** sections in the provided `lesson.md` file. Focus on understanding the limitations of traditional tools like Pandas and the architectural advantages of Polars.

**Guiding Questions:**

* Why is Pandas considered limited when handling large datasets in a data science or engineering context?  
* How does Polars leverage **Arrow arrays** and **multi-threading** to be more performant than Pandas?  
* What is the concept of processing data in "chunks," and how does this help when data exceeds available memory?

### **📝 Task 2: Visualizing Lazy Evaluation and Polars (20 Minutes)**

**Activity:** Open and review the `out_of_core.ipynb` notebook. **You do not need to run the code yet.** Instead, read through the code cells and markdown comments to trace the difference between eager execution (Pandas) and lazy execution (Polars).

**Focus your attention on these key components:**

1. **Reading Data:** Compare `pd.read_csv` with `pl.read_csv` and `pl.scan_csv`.  
2. **Lazy Evaluation:** Identify how the `.lazy()` method is used to define computation without immediately executing it.  
3. **Collection:** Look at the `.collect()` method and the `streaming=True` parameter.

**Guiding Questions:**

* In the notebook, Polars recommends `lazy` evaluation. What happens to the code execution when using this method compared to standard execution?  
* Look at the `scan_csv` function in the "Hands-on with Polars Out of Core Processing" section. How does this function differ from a standard read operation in terms of loading data into memory?

### **📝 Task 3: Conceptualizing DuckDB (10 Minutes)**

**Activity:** Briefly skim the **"Hands-on with DuckDB"** section at the end of `out_of_core.ipynb`.

**Guiding Questions:**

* How does DuckDB differ from a traditional Relational Database Management System (RDMS) regarding memory usage?  
* Review the SQL query structure in the notebook. How does DuckDB allow you to query a CSV file directly (e.g., `read_csv_auto`) without pre-loading it into a database?

## **🙌🏻 Active Engagement Strategies**

To deepen your retention, try one of the following while you review:

* **Concept Mapping:** Sketch a simple diagram showing the flow of data from *Disk (CSV)* \-\> *Chunks* \-\> *Processing (Polars/DuckDB)* \-\> *Result*, contrasting it with how Pandas loads everything into RAM at once.  
* **"Code Commentary":** Select a code block using `.collect(streaming=True)` in the notebook and write a brief comment explaining why streaming is necessary for the NYC Taxi Trip dataset (1.5GB).  
* **Scenario Matching:** Think of a recent project where your kernel crashed due to memory issues. How could `scan_csv` or DuckDB have prevented that error?

## Additional Material

- [Out of core data processing](https://pythonspeed.com/articles/data-doesnt-fit-in-memory/)
- [Pandas Memory Error](https://saturncloud.io/blog/how-to-fix-memoryerror-issues-when-using-pandas-in-python/)
- [Pandas Multiprocessing](https://saturncloud.io/blog/pandas-multiprocessing-apply-a-guide-for-data-scientists/)
- [Pandas 2.0 vs Polars](https://www.datacamp.com/tutorial/high-performance-data-manipulation-in-python-pandas2-vs-polars)

### **🙋🏻‍♂️ See you in the session\!**



