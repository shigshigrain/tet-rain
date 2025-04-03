FROM rust:1.85

RUN apt-get update && \
    apt-get -y install git && \
    apt-get -y install pkg-config && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rustup component add rls rust-analysis rust-src rustfmt clippy && \
    cargo install --locked cargo-edit cargo-watch
