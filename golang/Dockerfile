FROM surnet/alpine-wkhtmltopdf:3.7-0.12.5-full as builder

# Image
FROM golang:1.11.1-alpine3.7

RUN mkdir -p /usr/share/fonts/opentype/
COPY ./noto/  /usr/share/fonts/opentype/noto

RUN apk add --no-cache \
  libstdc++ \
  libx11 \
  libxrender \
  libxext \
  libssl1.0 \
  ca-certificates \
  fontconfig \
  freetype \
  ttf-dejavu \
  ttf-droid \
  ttf-freefont \
  ttf-liberation \
  ttf-ubuntu-font-family

COPY --from=builder /bin/wkhtmltopdf /bin/wkhtmltopdf
COPY --from=builder /bin/wkhtmltoimage /bin/wkhtmltoimage
COPY --from=builder /bin/libwkhtmltox* /bin/
