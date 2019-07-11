FROM ubuntu

WORKDIR /usr/app
COPY . .
RUN apt-get update && apt-get install -y curl 

CMD ["/bin/bash"]
CMD echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;