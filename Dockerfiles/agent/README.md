## Build Docker Image
```
git clone https://github.com/cyralinc/datadog-agent.git

cd datadog-agent/Dockerfile/agent/

AGENT_VERSION=7.23.0
GIT_BRANCH="cyral-release/$AGENT_VERSION-aptible"

git checkout $GIT_BRANCH

curl https://s3.amazonaws.com/apt.datadoghq.com/pool/d/da/datadog-agent_$AGENT_VERSION-1_amd64.deb -o datadog-agent_$AGENT_VERSION-1_amd64.deb

docker build --file amd64/Dockerfile --pull --target release --tag gcr.io/cyralpublic/cyral-datadog-agent-aptible:v0.1.0 .

docker push gcr.io/cyralpublic/cyral-datadog-agent-aptible:v0.1.0
```