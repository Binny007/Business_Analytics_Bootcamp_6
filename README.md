# Business_Analytics_Bootcamp_6


# Ranking Charts: A Comprehensive Guide

**Overview**

   --> This repository explores various ranking charts and their best practices using a case study on the World Happiness Dataset. It includes implementations, dos and don'ts, and insights into different visualization techniques.

   --> Additionally, a cheatsheet for visualization customization in Matplotlib and Seaborn is provided to enhance styling and presentation.

# Case Study: World Happiness Dataset

   The World Happiness dataset ranks countries based on happiness scores and other socio-economic indicators. This repository includes visualizations analyzing:

         * Top 10 happiest countries using bar charts.
      
         * Generosity rankings using a lollipop chart.
         
         * Comparison of multiple happiness indicators using a spider chart.

   **Objective:**
   
         Analyze global happiness rankings using different ranking charts.
   
   **Dataset Overview:**
   
         * The dataset includes happiness scores based on factors such as GDP per capita, social support, healthy life expectancy, freedom to make life choices, generosity, and perceptions of corruption.
         
         * Data visualization techniques will help understand country rankings effectively.

# 1️⃣ Bar Charts
   
   Bar charts are commonly used to visualize rankings by comparing categorical data.

   **✅ DO's:**
   
       * Use bar charts for comparing discrete categories.
       
       * Keep bars aligned to a common baseline.
       
       * Sort bars in descending order for better readability.
       
       * Use consistent color schemes.
       
       * Label bars clearly and use gridlines when necessary.
   
   
   **❌ DON'Ts:**
   
         * Avoid excessive use of colors.
         
         * Do not use 3D effects, as they can distort perception.
         
         * Avoid too many bars; consider aggregation if needed.
         
         * Do not use bars for continuous data.

   **🔹 Implementation:**

         import matplotlib.pyplot as plt
         plt.bar(x, y, color='skyblue')
         plt.show()


# 2️⃣ Lollipop Chart

   Lollipop charts provide a minimalistic alternative to bar charts, emphasizing ranking.

   **✅ DO's:**
   
         * Use when showing rank-based comparisons.
         
         * Keep circles large enough to be visible.
         
         * Maintain a simple and clean design.
         
         * Label key data points.
   
   **❌ DON'Ts:**
   
         * Avoid unnecessary embellishments.
         
         * Do not use when too many categories are involved.
         
         * Avoid overlapping markers.

   **🔹 Implementation:**

         plt.stem(x, y, linefmt='skyblue', markerfmt='orange')
         plt.show()
         

# 3️⃣ Spider Chart (Radar Chart)

   Spider charts compare multiple variables across different categories.

   *✅ DO's:**
   
         * Use when comparing multiple variables across different categories.
         
         * Normalize data to ensure consistency.
         
         * Keep the number of variables manageable (5-7 recommended).
         
         * Label axes clearly.
   
   **❌ DON'Ts:**
   
         * Do not use for a large number of categories.
         
         * Avoid cluttering with too many data points.
         
         * Do not use when exact numerical comparison is needed.

   **🔹 Implementation:**

         import numpy as np
         angles = [n / float(N) * 2 * np.pi for n in range(N)]
         ax.fill(angles, values, 'b', alpha=0.1)
         plt.show()


# 🎨 Cheatsheet for Customization

   For detailed customization options in Matplotlib and Seaborn, refer to the included cheatsheet file in the repository.

   **General Customizations**

      * Figure Size: plt.figure(figsize=(width, height))
      
      * Title & Labels: plt.title(), plt.xlabel(), plt.ylabel()
      
      * Legend: plt.legend(loc='best')
      
      * Grid: plt.grid(True)
      
      * Rotation: plt.xticks(rotation=angle)

   **Bar Charts**
   
      * Bar Color: plt.bar(x, y, color='skyblue')
      
      * Highlight Specific Bars: plt.bar(x, y, color=['orange' if val == max(y) else 'skyblue' for val in y])
   
   **Lollipop Charts**
   
      * Stem Color: plt.stem(x, y, linefmt='skyblue', markerfmt='orange')
      
      * Marker Size: plt.plot(x, y, 'o', markersize=8, color='red')
   
   **Spider Charts**
   
      * Polar Subplot: plt.subplot(111, polar=True)
      
      * Angle Calculation: angles = [n / float(N) * 2 * np.pi for n in range(N)]
      
      * Filling Area: ax.fill(angles, values, 'b', alpha=0.1)


   **General Customization**

         # Define the plot size
         fig, ax = plt.subplots(figsize=(15, 6))
         
         # Add a Vertical line
         ax.axvline(df.Total.median(), color='black', ls='dashed', label='Median Total Power')
         
         # Add a horizontal line
         ax.axhline(50, color='blue', ls='dotted', label='Line at frequency of 50')
         
         # Customize y-axis labels
         plt.yticks(ticks=y_pos, labels=data['Country name'])
         plt.yticks([0.3, 0.7], labels=['0.3', '0.7'], color='grey', size=7)
         
         # Customize x-axis labels
         plt.xticks(ticks=angles[:-1], labels=categories, rotation=0, color='black', size=12)
         
         # Set axis limits
         plt.ylim(0,1)
         plt.xlim(0,1)
         
         # Change font size
         ax.tick_params(axis='both', labelsize=15)
         
         # Add title and labels
         fig.suptitle('Happiness of the top 10 countries, ranked', fontsize=15)
         plt.xlabel('Countries', fontsize=15)
         plt.ylabel('Generosity Score', fontsize=15)
         
         # Plotting
         ax.legend()
         plt.show()
         
         # Seaborn theme
         import seaborn as sns
         sns.set_theme(style='darkgrid')


# 📌 Conclusion

   Ranking charts provide powerful insights when used correctly. Each chart type serves a specific purpose, and following best practices ensures clarity and effective communication.

**📂 Repository Content:**

* happiness.csv → Dataset containing happiness-related data.
* Ranking Charts Template.ipynb → Jupyter Notebook for creating ranking charts.
* Data Viz Customization Cheat Sheet.ipynb → Jupyter Notebook with tips and tricks for customizing data visualizations.
* README.md → This file, providing an overview of the repository.

Feel free to explore, contribute, and suggest improvements! 🚀
