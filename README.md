<h2>Car Price Prediction 🚗</h2>
<h4>Table of Content
<ul>
<li><a href="#demo">Demo</a></li>
<li><a href="#intro">Introduction</a></li>
<li><a href="#technical">Technical Aspects</a></li>
<li><a href ="#installation">Installation</a></li>
<li><a href="#model">Model Creation</a></li>
<li><a href="#">Flask App Creation</a></li>
<li><a href="#">Deployment</a></li>
<li><a href="#">Conclusion and Further Development</a></li>
<li><a href="#">Technologies Used</a></li>
<li><a href="#">Credits</a></li>
</ul>
<h3 id="demo">Demo</h2>
<img src="images/demo.png"/>
<p>Please Click <a href="https://carpricespredictionml.herokuapp.com/"> Here</a> to run the app</h3>
<h3 id="intro">Introduction</h3>
<p>This is a machine learning based app to predict the price of used Car.</p>
<p>The model of the app is based on <b>Random Forest Regressor</b> which is famous for its high accuracy. Basically it is an ensemble learning technique which takes some "n" base learners mainly <b>Decision Trees</b> and take best prediction based on votes</p>
<h4>Dataset used:</h4>
<p>I have used <a href="https://www.kaggle.com/nehalbirla/vehicle-dataset-from-cardekho">Car Dekho</a> Data from <a href='https://www.kaggle.com/'>Kaggle</a>.</p>
<h4>Understanding Data:</h4>
<p>Here is dataset snippet</p>
<img src="images/data.png"/>
<p>Dataset consist of various columns such as <i>Car_name</i>,<i>year</i>,<i>Selling_Price</i>,<i>Present_price</i> etc.</p>
<p>On the basis of this dataset we need to decide what should be the price of any second hand car. This is a regression task i.e. we need to predict continuous value from the data therefore we need to go with those algorithms which is good with this.</p> 

<h3 id='technical'>Technical Aspects</h3>
<p>This project is basically divided on 2 part</p>
<ol>
<li>Model Building (using Random Forest and other machine learning algorithms) </li>
<li>Model Deployment using Flask in Heroku Platform
</ol>
<h3 id="installation">Installation</h3>
<h4>Python Installation</h4>
<p>I worked in Anaconda Platform which you can visit by clicking <a href='https://www.anaconda.com/products/individual'>this website</a> to download anconda's individual edition</p>
<p>Please make a saparate enviroment before jumping into code</p> 
<p>Please install all the following pakages using <i>"pip install"</i>
<ul><li>sklearn</li><li>pandas</li><li>numpy</li><li>flask</li><li>matplotlib</li><li>seaborn</li></ul>

<h3 id="model">Model Creation</h3>
<p>Before training our model we need to clean and analyze our dataset. Let's see how we did it</p>
<h4>Data Cleaning and EDA</h4>
<p>I first decided to check null values in the dataset.</p>
<img src='images/nullcheck.png'/>
<p>So it's great! that we don't have any null values present in it.</p>
<p>Next let's check frequency of the cateogrical features in the dataset.</p>
<img src='images/categorical.png'/>
<p>So According to the above figure we have to convert <i>Seller_Type</i>,<i>Transmission</i> and <i>Fuel Type</i> into one hot vector so that we can perform numerical calculations on them</p>
<img src='images/one_hot_vector.png'/>
<p>Next we need to break the data into <b>Independet</b> and <b>Dependent</b> feature.</p>
<img src='images/independent.png'/>
<p>Since we are using Tree based learning algorithm so we do NOT required <b>Feature Engineering</b> or <b>Feature Scaling</b>. But if anyone want to work with any other algo they must need to first convert the features into its scalled form and then train the model.</p>
<p>Let's check the important feature in the dataset.</p>
<img src='images/feature_important.png'/>
<p>So clearly it shows that <i>"Owner"</i> feature not at all important for our model training so we decided to remove it from the training data. As it only increases the size without giving any value.</p>
