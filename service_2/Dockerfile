FROM python:3.11-slim

WORKDIR /app

# 1. Install system tools, install uv, symlink it, install Flask globally
RUN apt-get update && apt-get install -y --no-install-recommends \
    bash curl build-essential ca-certificates \
    && curl -LsSf https://astral.sh/uv/install.sh | bash \
    && ln -s /root/.local/bin/uv /usr/local/bin/uv \
    && uv pip install --system flask \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# 2. Copy your application code
COPY . .

# 3. Forward port
EXPOSE 8002

# 4. Run your app inside uv's environment
CMD ["uv", "run", "python", "app.py"]
