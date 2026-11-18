wget https://raw.githubusercontent.com/egunda/mediacdn-dashboard/refs/heads/main/mdashboard.json

gcloud monitoring dashboards create --config-from-file=mdashboard.json
