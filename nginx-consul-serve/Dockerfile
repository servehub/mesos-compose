FROM nginx:alpine

RUN rm -rf /etc/nginx/conf.d/*

COPY bin/consul-template /usr/local/bin/consul-template
COPY bin/serve-tools /usr/local/bin/serve-tools

COPY consul-template.conf /etc/consul/consul-template.conf
COPY nginx.conf /etc/nginx/nginx.conf
COPY consul-nginx.ctmpl /etc/consul/consul-nginx.ctmpl

VOLUME ["/data/nginx/cache"]

CMD ["/usr/local/bin/consul-template", "-config", "/etc/consul/consul-template.conf"]
