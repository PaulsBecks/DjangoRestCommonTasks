# DjangoRestCommonTasks
This is just a couple of 'how to ...' for myself to look up.


## File upload to FileField

To upload a file to a Django model you have to do:

1. Add ``enctype="multipart/form-data"`` to your html form like: 
``` html
<form action="<your_url>" method="POST" enctype="multipart/form-data">
    <input name="file" type="file" accept="application/pdf">
    <input type="submit">
</form>
```

2. Do what you want with that file it in ``request.FILES['file']``:

``` python
def post(self, request):
    s = FileSerializer(data=request.data)
    if s.is_valid():
        s.save()
        return Response(status=204)
    return Response(status=400)
```

