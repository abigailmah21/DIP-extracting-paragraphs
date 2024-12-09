# Paragraph Extraction in Python 
A python program to extract paragraphs under digital image processing.

## Introduction
The main purpose of this task is to identify and extract all the paragraphs from single, double, and triple-column papers, and sort them in the correct order for double-column and triple-column papers with minimum human intervention. Additionally, the code is designed to ignore the tables and figures when extracting the paragraphs.

## Methodology/ Proposed approach

*Step 1: Image Preprocessing*

The image is first converted into grayscale and gaussian blur is applied to the image to mitigate noise.

*Step 2: Column Detection*

The histogram of the image is analyzed to detect zero dips. The columns are then identified by the width of the dip.

*Step 3: Paragraph Detection*

Each column of the histogram is analyzed to detect individual paragraphs. We do so by segmenting out the dips of the histogram to determine the general area of the paragraphs.

*Step 4: Ignoring Tables & Figures (Removing images)*

From each segment we will then find the max height of each, we then add up the maximum heights to find the average max height. A value of 2000 is added to act as a buffer to account for any irregularity of the paragraphs, as any tables, figures (non-paragraphs) will have an irregularly high maximum height which we then can determine the segment to not be a paragraph; therefore, we could just exclude it.

