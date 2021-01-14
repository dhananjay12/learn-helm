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
helm repo index .
```


