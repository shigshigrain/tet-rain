FROM rust:1.85

RUN apt-get update && \
    apt-get -y install git && \
    apt-get -y install pkg-config && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    apt install -y vim clang cmake libssl-dev build-essential \
    libwebkit2gtk-4.0-dev curl wget libssl-dev libgtk-3-dev \
    libayatana-appindicator3-dev librsvg2-dev x11-apps

RUN rustup component add rls rust-analysis rust-src rustfmt clippy && \
    cargo install cargo-edit cargo-watch cargo-make sqlx-cli tauri-cli trunk && \
    rustup install nightly && \
    rustup target add wasm32-unknown-unknown

RUN cargo install create-tauri-app --locked

ENV RUST_BACKTRACE=1
