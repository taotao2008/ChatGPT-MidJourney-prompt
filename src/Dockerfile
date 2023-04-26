# Bundle Stage
FROM python:3.10.10-slim-buster
ENV URL_MJ_PROMPT=http://midjourney_api:5000/api/send_and_receive_async
ENV OPENAI_KEY=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
RUN apt-get update && apt-get install -y ca-certificates
RUN apt-get install git -y
WORKDIR /opt/
RUN git clone -b wali-v1.0.0 https://oauth2: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@github.com/taotao2008/ChatGPT-MidJourney-prompt.git
WORKDIR /opt/ChatGPT-MidJourney-prompt/src
RUN git pull
RUN pip install --no-cache-dir -r requirements.txt
COPY ./docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh
ENTRYPOINT ["/docker-entrypoint.sh"]