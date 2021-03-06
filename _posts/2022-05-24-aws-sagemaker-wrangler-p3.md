---
keywords: fastai
description: A detailed guide on AWS SageMaker Data Wrangler to prepare data for machine learning models. This is a five parts series where we will prepare, import, explore, process, and export data using AWS Data Wrangler. You are reading **Part 3:Explore data with Data Wrangler visualizations**.
title: Data Preparation with SageMaker Data Wrangler (Part 3)
toc: true 
badges: true
comments: true
categories: [aws, ml, sagemaker]
keyword: [aws, ml, sagemaker, wrangler]
image: images/copied_from_nb/images/2022-05-24-aws-sagemaker-wrangler-p3.jpeg
nb_path: _notebooks/2022-05-24-aws-sagemaker-wrangler-p3.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-05-24-aws-sagemaker-wrangler-p3.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><img src="/myblog/images/copied_from_nb/images/2022-05-24-aws-sagemaker-wrangler-p3.jpeg" alt=""></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Enviornment">Enviornment<a class="anchor-link" href="#Enviornment"> </a></h1><p>This notebook is prepared with Amazon SageMaker Studio using <code>Python 3 (Data Science)</code> Kernel and <code>ml.t3.medium</code> instance.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="About">About<a class="anchor-link" href="#About"> </a></h1><p>This is a detailed guide on using <strong>AWS SageMaker Data Wrangler</strong> service to prepare data for machine learning models. SageMaker Data Wrangler is a multipurpose tool with which you can</p>
<ul>
<li>import data from multiple sources</li>
<li>explore data with visualizations</li>
<li>apply transformations</li>
<li>export data for ml training</li>
</ul>
<p>This guide is divided into five parts</p>
<ul>
<li><a href="https://hassaanbinaslam.github.io/myblog/aws/ml/sagemaker/2022/05/17/aws-sagemaker-wrangler-p1.html">Part 1: Prepare synthetic data and place it on multiple sources</a></li>
<li><a href="https://hassaanbinaslam.github.io/myblog/aws/ml/sagemaker/2022/05/23/aws-sagemaker-wrangler-p2.html">Part 2: Import data from multiple sources using Data Wrangler</a></li>
<li><strong>Part 3: Explore data with Data Wrangler visualizations (You are here)</strong></li>
<li><a href="https://hassaanbinaslam.github.io/myblog/aws/ml/sagemaker/2022/05/25/aws-sagemaker-wrangler-p4.html">Part 4: Preprocess data using Data Wrangler</a></li>
<li><a href="https://hassaanbinaslam.github.io/myblog/aws/ml/sagemaker/2022/05/26/aws-sagemaker-wrangler-p5.html">Part 5: Export data for ML training</a></li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Part-3:-Explore-data-with-Data-Wrangler-visualizations">Part 3: Explore data with Data Wrangler visualizations<a class="anchor-link" href="#Part-3:-Explore-data-with-Data-Wrangler-visualizations"> </a></h1><p>In this post, we will use SageMaker Data Wrangler to create some visualizations for exploratory data analysis (EDA). Open the <code>customer-churn.flow</code> from part-2. It is also available on GitHub <a href="https://github.com/hassaanbinaslam/myblog/blob/master/_notebooks/datasets/2022-05-23-aws-sagemaker-wrangler-p2/customer-churn.flow">here</a>. We will create a histogram to explore the frequency distribution of daily calls. Once the flow process is open on the Data Flow UI it will look like this</p>
<p><img src="/myblog/images/copied_from_nb/images/2022-05-24-aws-sagemaker-wrangler-p3/customer-churn.png" alt="customer-churn"></p>
<p>Click on the 2nd join plus sign and select 'Add Analysis'. From the next analysis UI select</p>
<ul>
<li>Analysis Type = Histogram</li>
<li>Analysis Name = call_minutes_churn</li>
<li>X_axis = day_min</li>
<li>Facet by = Churn?</li>
</ul>
<p>Click Preview and Data Wrangler will create the following histogram</p>
<p><img src="/myblog/images/copied_from_nb/images/2022-05-24-aws-sagemaker-wrangler-p3/call_minutes_chrun.png" alt="call_minutes_chrun"></p>
<p>From this histogram you can see that customers whose calls duration are 4 minutes or less are more likely to stay, and customer having call duration longer than 4 minutes are more likely to churn. Save the flow to return back to main Data Flow UI.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Preview-ML-model-performance-using-Quick-Model">Preview ML model performance using Quick Model<a class="anchor-link" href="#Preview-ML-model-performance-using-Quick-Model"> </a></h2><p>Quick Model is another great feature of SageMaker wrangler with which we can quickly train a <strong>Random Forrest Classification</strong> model and analyze the importance of features. For this again click on the plus sign against the 2nd Join, and select <em>Add Analysis</em>. Then from the Analysis UI select</p>
<ul>
<li>Analysis Type = Quick Model</li>
<li>Analysis Name = Quick model</li>
<li>Label = Churn?</li>
</ul>
<p><em>Label</em> is our target identifier. Click preview. Data Wrangler will take around a minute to train the model, and will provide a chart with feature importances.</p>
<p><img src="/myblog/images/copied_from_nb/images/2022-05-24-aws-sagemaker-wrangler-p3/quick_model.png" alt="quick_model.png"></p>
<p>From this feature importance chart, we can see that the <code>day_mins</code> and <code>night_charge</code> features have the highest importance. It also shows that the model has achieved F1 score of 0.841 on the test data. We can take this model as a baseline and work on the important features and model tuning to improve its performance. Click Save to return to the main Data Flow UI.</p>
<h1 id="Summary">Summary<a class="anchor-link" href="#Summary"> </a></h1><p>In this post, we saw that we can quickly create visualizations from Data Wrangler to do our EDA work. There are many other built-in analysis reports available (check Data Leakage and Data Quality reports) that can quickly provide a very detailed analysis of the data. The <code>customer-churn.flow</code> file is available on GitHub <a href="https://github.com/hassaanbinaslam/myblog/blob/master/_notebooks/datasets/2022-05-23-aws-sagemaker-wrangler-p2/customer-churn-p3.flow">here</a>. In the next post, we will perform some preprocessing and transformations to make our data ready for ML training.</p>

</div>
</div>
</div>
</div>
 

