FROM golang:1.16-alpine AS builder

ENV APP_HOME /go/src 
WORKDIR $APP_HOME
ENV PATH="/go/bin:${PATH}"
ENV GO111MODULE=on
ENV GOFLAGS=-mod=vendor
ADD ./ $APP_HOME
RUN go build -o $APP_HOME/desafio1
RUN ls $APP_HOME
RUN pwd


FROM scratch
ENV APP_HOME /go/src 
WORKDIR $APP_HOME
COPY --from=builder $APP_HOME/desafio1 $APP_HOME/desafio1
EXPOSE 8000
CMD ["./desafio1"]