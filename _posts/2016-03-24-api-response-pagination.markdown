---
title:  "API response pagination"
date:   2016-03-24 08:05:00
summary: Splitting up data into multiple HTTP requests, for limiting HTTP Response size.
---

### Pagination, what for ?
Splitting up data into multiple HTTP requests, for limiting HTTP Response size.

### The reason ?

1. Downloading more takes longer.
2. Trying to return 1000,000 into infinity records in one go might takes longer into eternity.
3. "Presentation logic iterating over 1000,000 into infinity records is fun" - Nobody, ever.
