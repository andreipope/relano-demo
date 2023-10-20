The sections below list all new features, enhancements, and changes to the platform, in chronological order.

## Version 1.2

If you have used the 1.2 version of the API, please refer to the following section for important information regarding the changes.

### New features

Version 1.2 of the Twelve Labs Video Understanding Platform introduces the following new features:

- The Pegasus video understanding engine has been released. You can now generate concise textual representations for your videos, including but not limited to titles, summaries, chapters, and highlights. See the [Generate](/v1.2/docs/generate-api-guide) section for more information.
- You can now upload videos from external providers. Currently, only YouTube is supported as an external provider, but we will add support for additional providers in the future. See the [Upload from external providers](doc:upload-from-external-providers) page for details.

### Updates

This section lists the differences between version 1.1.2 and version 1.2 of the Twelve Labs Video Understanding API.

- When you make an API call, make sure that you specify the `1.2` version in the URL.  
  The URL should look similar to the following one: `https://https://api.twelvelabs.io./v1.2/{resource}/{path_parameters}?{query_parameters}`. For more details, see the [Call an endpoint](/reference/api-reference#call-an-endpoint) section.
- To enable the utilization of multiple engines for an index, the following changes have been made:
  - **POST** `/indexes`: The `engine_id` and `indexing_options` parameters of the request have been deprecated. Instead, you can now define the engine configuration as a list of objects. See the [Create an index](/reference/create-index) page for details.
  - **GET** `/indexes/:index_id`:  The `engine_id` field in the response has been superseded by an array of objects named `engines`. See the [Retrieve an index](ref:retrieve-index) page for details.
  - **GET** `/indexes`: 
    - The `engine_id` field in the response has been superseded by an array of objects named `engines`. See the [List indexes](ref:list-indexes) page for details.
    - The `engine_family` query parameter has been introduced, allowing you to filter by engine family.
    - The `index_options` query parameter has been marked for deprecation. You can still use it in this version of the API, but it will be deprecated in a future release. Instead, use `engine_options` or `engine_family`.
  - **GET**`/engines`: The `allowed_index_option` field in the response has been renamed to `allowed_engine_options`. See the [List engines](ref:list-engines) page for details.

  