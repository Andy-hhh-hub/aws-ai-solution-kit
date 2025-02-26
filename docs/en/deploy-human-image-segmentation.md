---
feature_id: HumanImageSegmentation
feature_name: Human Image Segmentation
feature_endpoint: human_image_segmentation
deployment_time: 15 Minutes
destroy_time: 9 Minutes
sample_image: Image URL address
feature_description: Segment human bodies from background and return the alpha channel
feature_scenario: It can be applied to photo background replacement, post-processing, ID photo production, portrait keying beautification, background defocusing and many other scenarios.
---

{%
  include "include-deploy-description.md"
%}

## REST API Reference

- HTTP request method: `POST`

- Request body parameters

| **Name**  | **Type**  | **Required** |  **Description**  |
|----------|-----------|------------|------------|
| url | *String* |Choose one of the two parameters with img, the priority is higher than the URL|Supports HTTP/HTTPS and S3 protocols. Requires the image format to be jpg/jpeg/png/bmp with the longest side not exceeding 4096px.|
| img | *String* |Choose one of two parameters with url|Base64 encoded image data|

- Example JSON request

``` json
{
"url": "{{page.meta.sample_image}}"
}
```

``` json
{
"img": "Base64-encoded image data"
}
```

- Response parameters

| **Name** | **Type** | **Description**  |
|----------|-----------|------------|
|result    |*String*   |Background-removed Base64-encoded alpha channel image data|

- Example JSON response

``` json
{
  "result": "Background-removed Base64-encoded alpha channel image data"
}
```

{%
  include-markdown "include-deploy-code.md"
%}

{%
  include "include-deploy-cost.md"
%}

{%
  include-markdown "include-deploy-uninstall.md"
%}
