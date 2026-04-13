"Videos" have 3 things to worry about:

Metadata: The title, description, and other information about the video
Thumbnail: An image that represents the video
Video: The actual video file      


mimeTypes are a way to identify the file type and extenstion and it show like this fileType/extenstion example : image/png

when the browser work with files it will cache them and one of the way to refatch is to use change url (add some query string )
and by that it will refresh the file. we use this when we udpate file but the the id of video stays the same means the browser 
thinks it is the same

Query strings are a great way to brute force cache controls as the client - but the best way (assuming you have control of the server, and c'mon, we're backend devs), is to use the Cache-Control header. Some common values are:

no-store: Don't cache this at all
max-age=3600: Cache this for 1 hour (3600 seconds)
stale-while-revalidate: Serve stale content while revalidating the cache
no-cache: Does not mean "don't cache this". It means "cache this, but revalidate it before serving it again"
