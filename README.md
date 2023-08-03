# matpotlib-challenge

Resources

#used code from Chat GPT
duplicate_mice_df = mouse_metadata_complete_df[mouse_metadata_complete_df.duplicated(subset=["Mouse ID", "Timepoint"])]["Mouse ID"].unique()
duplicate_mice_df

# Create a clean DataFrame by dropping the duplicate mouse by its ID.
# https://stackoverflow.com/questions/14057007/remove-rows-not-isinx
clean_df = mouse_metadata_complete_df[mouse_metadata_complete_df["Mouse ID"].isin(duplicate_mice_df)==False]

# https://pandas.pydata.org/pandas-docs/version/0.22/generated/pandas.core.groupby.DataFrameGroupBy.agg.html
summary_aggregate =  clean_df.groupby(['Drug Regimen'])[['Tumor Volume (mm3)']].agg(['mean', 'median', 'var', 'std', 'sem'])
summary_aggregate

#rotation = chat GPT
plt.xticks(tick_locations, labels, size = 12, rotation = 60)

# Resource for entire Quartiles, Outliers and Boxplots section : https://github.com/redeat17/Matplotlib-Challenge/blob/master/pymaceuticals_starter.ipynb


# Generate a scatter plot of mouse weight vs. the average observed tumor volume for the entire Capomulin regimen
# https://github.com/ermiasgelaye/Matplotlib-Challenge/blob/master/Pymaceuticals/pymaceuticals_starter.ipynb
#chat GPT
avg_capm_vol =Capomulin_df.groupby(['Mouse ID']).mean(numeric_only=True)


# Resource for entire Correlation and Regression section
#https://github.com/redeat17/Matplotlib-Challenge/blob/master/pymaceuticals_starter.ipynb

