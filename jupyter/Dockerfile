FROM python:3.12.10-bookworm

ENV TZ=Asia/Tokyo

RUN apt update && apt install -y libgl1

COPY requirements.txt /tmp
RUN pip install -r /tmp/requirements.txt

RUN adduser ubuntu
USER ubuntu
WORKDIR /home/ubuntu

RUN mkdir -p wks
WORKDIR /home/ubuntu/wks
RUN git clone https://github.com/kmeisthax/gridfinity-cadquery.git

WORKDIR /home/ubuntu

ENTRYPOINT ["jupyter", "lab", "--port=80", "--ip=*"]
