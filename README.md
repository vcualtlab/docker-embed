# Docker Embed
Quick plugin for Discourse to allow embedding in an iframe. For background see [this thread](https://meta.discourse.org/t/x-frame-options-sameorigin-header-prevents-embedding/14928). Plugin should be added to a Discourse Docker installation by adding the repo URL in the hooks section of your container configuration file like the following example:
```
hooks:
  after_code:
    - exec:
        cd: $home/plugins
        cmd:
          - mkdir -p plugins
          - git clone https://github.com/discourse/docker_manager.git
          - git clone https://github.com/vcualtlab/docker-embed
```

This plugin will add the appropriate headers to allow your Discourse install to be embedded within another site on a different domain and for that domain to access JSON files. You'll want to change the domain to your domain or use * to allow all domains access.
