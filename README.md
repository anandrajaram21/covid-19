# Covidash

Covidash is an open source, community driven, COVID-19 dashboard that not only shows the daily statistics of the growing pandemic, but also forecasts the growth of the pandemic.

The forecasts are generated by a Convolutional Network, with the MAPE consistently remaining below 5% for all countries.

## Getting Started

### Prerequisites

- The program will run without any issues on any computer, but for a smooth performance, we recommend a system with atleast 4 GB of memory, and atleast 2 CPU cores.
- You must have either Python or Docker(recommended) installed.
- You must have npm and node installed to take a look at the documentation.
- You must have git installed to clone this repository, or you can just download the zip file.

### Basic Setup

#### 1. On Linux/macOS

##### a. If you have Docker installed

- Run the following commands on a UNIX based system

```
chmod +x deploy.sh
./deploy.sh
```

- Open a browser and navigate to 0.0.0.0:8050, and you will see the dashboard

##### b. If you have only Python installed

- Run the following commands on a UNIX based system to get the python environment ready. We are using venv here, as its very simple to get started with

```
python3 -m venv env # Use python instead of python3 if the command throws an error
source env/bin/activate
pip install -r requirements.txt
```

- Navigate to the web_app directory, and start the app with the following commands

```
cd src/web_app/
gunicorn --bind :8050 --workers 2 --threads 8 app:server # Change the number of workers and threads to your liking
```

- Open a browser and navigate to 0.0.0.0:8050, and you will see the dashboard

#### 2. On Windows

##### a. If you have Anaconda installed (recommended for easy installation)

- Run the following commands in Anaconda Prompt

```
cd <path of the cloned folder>
conda env create -f environment_windows.yml
conda activate covid
python .\src\web_app\app.py # or change directory to web_app and run `python app.py`
```

- Open a browser and navigate to 0.0.0.0:8050, and you will see the dashboard

### Documentation

- Run the following commands to start the docusaurus project and navigate to localhost:3000 on your browser.

```
cd docs
npm start
```

### Technologies Used

- Python is the primary programming language used
- Plotly Dash is the framework used to build the web app. (Plotly Dash uses Flask in its underlying implementation, and so is very fast)
- Keras is the main library used to make the model (CNN) that forecasts the cases. Some other libraries like Facebook Prophet and SciKit-Learn were used, but Keras offered the most flexibility along with ease of learning and experimentation.
- Plotly is the library used for all the data visualizations and graphs that you see on the dashboard.
- Jupyter Notebooks were used widely for testing our models and our visualizations.
- Docusaurus was used to make the project documentation.

### **[Presentaion](https://github.com/Majimearun/Covid-19-Outbreak-Analysis)**
