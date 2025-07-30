---
Title: Remote Sensing of Sewing Work Levels Using a Power Monitoring System
Year: 2020
Authors: Woo-Kyun Jung, Yong-Chul Park, Jae-Won Lee, Eun Suk Suh
tags:
  - garment
  - production
  - line
  - level
  - of
  - difficulty
  - level
  - of
  - skill
  - optimization
  - weight
  - factor
  - power
  - monitoring
  - system
  - Similar-Work
Processed: true
---
Zotero PDF Link: [Full Text PDF](zotero://select/library/items/UWJ5NDUL) 
Related::  

### Persistent Notes 
%% begin notes %% 
**System**
The paper proposes a power monitoring system (PMS) that is attached to sewing machines to remotely collect and analyze power consumption data. This system enables the extraction of working times for sewing tasks without requiring any modification to the sewing machines or additional equipment. The collected data is transmitted via a wireless network to a cloud server, where pattern analysis algorithms (such as symbolic aggregate approximation and dynamic time warping) are applied to identify the working time and quality of sewing operations. This allows for the quantitative measurement and visualization of the level of skill (LS) of sewing machine operators and the level of difficulty (LD) of sewing tasks in real time, facilitating optimization of garment production lines (from [page 3](da://viewer/dell43ufwd9dfgxn/3) to [page 6](da://viewer/dell43ufwd9dfgxn/6)).

**Architecture and Features**
1. **Non-intrusive Power Monitoring**: The PMS connects to the sewing machine’s power plug without requiring any modification to the machine or additional equipment. It uses current sensors and Wi-Fi communication modules to collect power consumption data at low cost ([page 4](da://viewer/dell43ufwd9dfgxn/4)).
    
2. **Wireless Communication and Cloud Integration**: The collected power consumption data are transmitted via a wireless network to a cloud server for analysis, enabling remote monitoring and data storage ([page 4](da://viewer/dell43ufwd9dfgxn/4)).
    
3. **Pattern Analysis Algorithms**: The system applies symbolic aggregate approximation (SAX) and dynamic time warping (DTW) algorithms to analyze the power consumption patterns. These algorithms extract working time information for each unit sewing process by identifying power usage patterns corresponding to sewing and non-sewing activities ([page 5](da://viewer/dell43ufwd9dfgxn/5)).
    
4. **Linkage with Manufacturing Execution System (MES)**: The extracted working time data are linked with operator names, process names, and theoretical or existing work time information stored in the MES. This linkage allows the creation of baselines for operators and tasks based on theoretical or historical data ([page 5](da://viewer/dell43ufwd9dfgxn/5)).
    
5. **Quantification of Skill Level (LS) and Difficulty Level (LD)**: Using the matched data matrix, the system calculates LS and LD scales by correcting the baseline with real-time measurements of work time and defect rates, thus quantifying operator skill and task difficulty numerically ([page 5](da://viewer/dell43ufwd9dfgxn/5)).
    
6. **Deployment and Validation**: The system was applied to 20 garment production lines with about 50 operators, and data from approximately 1000 sewing machines were analyzed to verify accuracy and stability ([page 4](da://viewer/dell43ufwd9dfgxn/4)).

**Results**
1. The PMS successfully measured the working time and quality of sewing tasks, enabling the derivation of each operator’s level of skill (LS) and each task’s level of difficulty (LD) based on these measurements (from [page 9](da://viewer/dell43ufwd9dfgxn/9) to [page 10](da://viewer/dell43ufwd9dfgxn/10)).
    
2. The experimental results revealed significant differences between expert-assigned and PMS-derived LS and LD weight factors:
    
    - The LS weight factor proposed by experts was about 15% lower than that indicated by the experimental results.
    - The LD weight factor proposed by experts was about 15% to 40% higher than that indicated by the experimental results ([page 9](da://viewer/dell43ufwd9dfgxn/9) and [page 10](da://viewer/dell43ufwd9dfgxn/10)).
3. The PMS allowed for reliable data collection and analysis from approximately 1000 sewing machines, demonstrating its accuracy and stability ([page 4](da://viewer/dell43ufwd9dfgxn/4) and [page 10](da://viewer/dell43ufwd9dfgxn/10)).
    
4. The system enabled continuous and large-scale data collection without operators being aware of the measurement, overcoming limitations of manual measurement methods and allowing accumulation of big data for more accurate analysis over time ([page 10](da://viewer/dell43ufwd9dfgxn/10)).
    
5. The PMS measurements provided a quantitative evaluation of otherwise subjective expert judgments, which can be applied to optimize operator arrangement and improve garment production line productivity ([page 9](da://viewer/dell43ufwd9dfgxn/9) and [page 10](da://viewer/dell43ufwd9dfgxn/10)).
    
6. The study confirmed that higher operator skill levels correspond to shorter working times and higher quality, while higher task difficulty corresponds to lower quality but not necessarily longer working times, indicating that difficulty relates more to technical challenge than time required (from [page 7](da://viewer/dell43ufwd9dfgxn/7) to [page 8](da://viewer/dell43ufwd9dfgxn/8)).

**Shortcomings**
- no quality measurement, my work has the option to easily integrate data for quality
- 
 %% end notes %% 

### In-text annotations 



%% Import Date: 2025-07-11T15:30:04.012+02:00 %%
