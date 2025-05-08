FROM oven/bun:latest

# RUN bun install && bun i -D wxt
RUN apt-get update && apt-get install -y wget gnupg \
  && wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | apt-key add - \
  && echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list \
  && apt-get update \
  && apt-get install -y google-chrome-stable

# # Create user 'bun'
# RUN useradd -m bun

# (Optional) Give 'bun' sudo privileges if needed
RUN apt-get update && apt-get install -y sudo && apt-get install -y git && echo 'bun ALL=(ALL) NOPASSWD:ALL' > /etc/sudoers.d/bun && chmod 0440 /etc/sudoers.d/bun

# Set user as default
USER bun

# # Set working directory
# WORKDIR /home/bun

CMD [ "sleep", "infinity" ]
# CMD [ "bun", "dev" ]