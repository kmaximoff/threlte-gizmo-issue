#Issue 

After installing all dependencies
If you run npm run dev
You will see no Gizmo is rendered in UI, but top left corner of scene is still works as gizmo (hidden)
In Scene.svelte file if you hide CustomRenderer by commenting it. Gizmo will be rendered properly.

FYI. This is simplified code, in my app. I use CustomRenderer in Nested component, that is placed in scene and I use it to render selected object in the scene. 

THANK YOU FOR YOUR HELP!

Regards

Kamran