---
layout: project
type: project
image: img/employee_retention/employee-retention.jpg
title: "Employee Retention Prediction using Random Forest Classifier"
date: 2023/07/24
published: true
labels:
  - Python
  - Matplotlib
  - Scikit Learn
  - Pandas
  - Flask
  - Jupyter Notebook
summary: "Led the development of an employee retention prediction model using the Random Forest Classifier, based on the IBM HR dataset from Kaggle, in collaboration with an HR specialist for practical relevance."
---

<img class="img-fluid" src="../img/employee_retention/transparent.png">

I led the development of an employee retention prediction model using the Random Forest Classifier as part of a research project. This project utilized the IBM HR dataset from Kaggle and involved collaboration with an HR specialist to ensure practical relevance.

Our objective was to address the critical issue of employee retention through machine learning techniques. We sourced data from the IBM HR dataset on Kaggle, which provided comprehensive insights into employee demographics, performance, and turnover.

We developed an interactive web application to enhance the system's usability and accessibility. This web application offers an intuitive interface for users to interact with the model, explore various metrics, and gain insights into the factors driving employee retention. Key features of the web app include visual representations of the model's predictions, such as bar graphs, box plots, univariate analysis (KDE plot, violin plot), confusion matrix, correlation heatmap, and variable importance plots.

Throughout this project, I gained experience with various tools and technologies, including:

- Programming languages: Python

- Libraries: Seaborn, Matplotlib, Plotly, Plotly Dash, Scikit Learn, Pandas

- Framework: Flask

- Development environments: Jupyter Notebook, Google Colab

Combining practical insights from an HR specialist with our technical expertise, this project not only demonstrates the potential of machine learning in tackling real-world business challenges but also provides a valuable tool for organizations to better understand and address employee retention.

Here is some part of the code that illustrates we implemented the variable importance using Plotly:

```python
var_imp_inputs = df_visuals[bd.universal_features]
var_imp_target = df_visuals[bd.universal_target]
var_rf_model = bd.loaded_rf_model

var_imp = pd.DataFrame({
    'features': var_imp_inputs.columns,
    'importance': var_rf_model.feature_importances_
}).sort_values('importance', ascending=False)

# Create Plotly figure
color_count = len(var_imp['features'].unique())
var_imp_fig = px.bar(var_imp, x='importance', y='features', orientation='h',
             title='Variable Importance for our Random Forest Model',
             labels={'importance': 'Importance', 'features': 'Variables'},
             color='features',
             color_discrete_sequence=px.colors.qualitative.Set2)

var_imp_fig.update_layout(
    legend=dict(bgcolor='#FFF9F5', bordercolor='black', borderwidth=0.5)
)

var_imp_container = dbc.Container(
    [html.Hr(), html.H3('Variable Importance'), dcc.Graph(figure=var_imp_fig, style={'border': '1px solid black', 'margin': '10px'})]
)
```
 
