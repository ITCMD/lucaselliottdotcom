---
title: "Projects"
build:
  render: never        # the section itself produces no page
  list: local
cascade:
  build:
    render: never      # individual projects produce no page (they link out)
    list: local        # ...but still appear in the projects list
---
