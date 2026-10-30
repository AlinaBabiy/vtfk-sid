# Капсула С.І.Д. — багатоетапна збірка
FROM rust:1.79 AS build

WORKDIR /src
COPY sid/ .
RUN cargo build --release

FROM debian:12-slim

COPY --from=build /src/target/release/sid /usr/local/bin/sid

CMD ["sid"]