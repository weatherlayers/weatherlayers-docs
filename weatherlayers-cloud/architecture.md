# Architecture

WeatherLayers Cloud is a caching proxy with no periodic preloading.

When any user accesses a file for the first time, this when the file is downloaded from the upstream data source, processed and cached. Each such first request is expected to take a longer time to finish, depending on the upstream data source response time. All subsequent requests for the same file are served from the cache, either WeatherLayers internal cache or Cloudflare.

This optimises for common usage pattern of users who access the current files or closer forecast offsets over further future forecast offsets.

WeatherLayers Cloud doesn’t support an automated scripted usage requesting all forecast offsets upfront on a periodical schedule.
