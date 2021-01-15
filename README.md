# learning-helm

My helm learninig

## How to Serve Charts

`docs` folder is just to serve generic chart.

GitHub allows you to serve static web pages in two different ways:

* By configuring a project to serve the contents of its docs/ directory
* By configuring a project to serve a particular branch

I took the first approach. Follow https://helm.sh/docs/topics/chart_repository/ for more details.

Basically, a chart repository consists of packaged charts and a special file called index.yaml.

Copy the charts the docs folder and to create index.yaml use:

```
helm repo index --url https://dhananjay12.github.io/learn-helm/ --merge index.yaml .
```

To add this repo to locally

```
helm repo add mygithubcharts https://dhananjay12.github.io/learn-helm/
```

Check using:

```
helm repo list
```

If you run 

```
helm search repo generic-chart
```
Output will be something like 
```
NAME                            CHART VERSION   APP VERSION     DESCRIPTION
mygithubcharts/generic-chart    0.0.1           1.0.0           Helm chart for deploying basic applications
```

Install by:

```
helm install local mygithubcharts/generic-chart --version=0.0.1
```
