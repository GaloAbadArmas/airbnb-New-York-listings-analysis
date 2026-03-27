# airbnb-New-York-listings-analysis
This project analyzes an Airbnb listings dataset to explore market structure, room type distribution, review activity, and listing availability across New York City boroughs.
># Libraries

import kagglehub
import pandas as pd
import os
import matplotlib.pyplot as plt
import seaborn as sns

# Upload from Kaggle

path = kagglehub.dataset_download("arianazmoudeh/airbnbopendata")

files = os.listdir(path)
print("Archivos:", files)
<
