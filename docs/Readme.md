### Hosting helm charts via github

Helm charts repository is nothing but bunch of zip files served by a server.
Its mostly static data. Follow below steps at root directory, and get your
PR merged. Make sure that you bump up chart versions also.

Following: https://docs.helm.sh/developing_charts/#hosting-chart-repositories

NOTE: Bump up chart versions in `Chart.yaml` before proceeding.

~~~sh
# First create zip files for charts
cd /path/to/cloned/repo/of/helm-charts
helm package agent

# Now move generated packages to docs folder
mv agent-*.tgz docs

# Update index file in docs folder
cd docs
helm repo index --url=https://helm-charts.getdockup.com .
~~~


Now commit changes, open a PR and get it merged. Ensure that you change
version of charts before publishing.
