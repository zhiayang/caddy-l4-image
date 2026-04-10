FROM docker.io/library/caddy:builder-alpine AS builder

RUN xcaddy build                              \
	--with github.com/mholt/caddy-l4          \
	--with github.com/caddy-dns/dnsimple      \
	--with github.com/mholt/caddy-events-exec

FROM docker.io/library/caddy:alpine
COPY --from=builder /usr/bin/caddy /usr/bin/caddy
