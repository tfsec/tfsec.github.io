---
title: Installation
subtitle:
author: edwin
tags: [agent]
---

Install an agent by running the following command:  

```bash
wget -c https://github.com/q-assistant/agent/releases/download/v0.0.1-alpha0/agent_linux_amd64.tar.gz -O - | tar -xz && \
cd ~/.q && sudo cp agent.conf /etc/supervisor/conf.d
```