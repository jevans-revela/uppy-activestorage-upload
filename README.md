# uppy-activestorage-upload

<img src="https://uppy.io/images/logos/uppy-dog-head-arrow.svg" width="120" alt="Uppy logo: a superman puppy in a pink suit" align="right">

The ActiveStorage Upload plugin handles Ruby on Rails ActiveStorage direct uploads with Uppy.

## Example

Add this line to your HEAD tag.
```erb
<%= tag.meta name: "direct-upload-url", content: rails_direct_uploads_path %>
```
In a Rails API environment you can get the aforementioned value with `Rails.application.routes.url_helpers.rails_direct_uploads_path`, it's usually something like `"/rails/active_storage/direct_uploads"`. Add a full URL for `directUploadUrl` later, if necessary.

Then use `ActiveStorageUpload` as an Uppy plugin in your Javascript pack.

```js
import Uppy from '@uppy/core'
import ActiveStorageUpload from '@excid3/uppy-activestorage-upload'

let uppy = new Uppy(options)
uppy.use(ActiveStorageUpload, {
  directUploadUrl: document.querySelector("meta[name='direct-upload-url']").getAttribute("content")
})
```

## Installation

```bash
yarn add @excid3/uppy-activestorage-upload
# or
npm install @excid3/uppy-activestorage-upload --save
```

We recommend installing from yarn and then using a module bundler such as [esbuild](https://esbuild.github.io/).

## License

[The MIT License](./LICENSE).
