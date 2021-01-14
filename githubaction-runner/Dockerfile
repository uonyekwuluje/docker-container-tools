FROM ubuntu:18.04

ARG RUNNER_VERSION="2.263.0"

RUN apt-get update -y && apt-get upgrade -y && useradd -m docker
RUN apt-get install -y curl jq build-essential libssl-dev libffi-dev python3 python3-venv python3-dev apt-utils
RUN mkdir /opt/actions-runner && cd /opt/actions-runner \
    && curl -O -L https://github.com/actions/runner/releases/download/v${RUNNER_VERSION}/actions-runner-linux-x64-${RUNNER_VERSION}.tar.gz \
    && tar xzf ./actions-runner-linux-x64-${RUNNER_VERSION}.tar.gz
RUN chown -R docker:docker /opt/actions-runner && /opt/actions-runner/bin/installdependencies.sh

COPY start.sh start.sh

RUN chmod +x start.sh

USER docker

ENTRYPOINT ["./start.sh"]
