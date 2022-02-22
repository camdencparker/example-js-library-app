<template>
  <div id="upload">
    <h1>Hello</h1>
  </div>
</template>

<script>
import Uppy, { XHRUpload, DragDrop } from 'uppy'

// And their styles (for UI plugins)
// With webpack and `style-loader`, you can import them like this:
import '@uppy/core/dist/style.css'
import '@uppy/dashboard/dist/style.css'

const uppy = new Uppy()
  .use(Dashboard, {
    trigger: '#select-files',
  })
  .use(XHRUpload, { endpoint: 'https://api2.transloadit.com' })

uppy.on('complete', (result) => {
  console.log('Upload complete! We’ve uploaded these files:', result.successful)
})
</script>
