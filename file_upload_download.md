# File upload to FileField

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


#Download File from FileField

To download a pdf-file saved in a model instance do:

``` python
    file = File.objects.get(pk=pk)
    filename = file.file.name.split('/')[-1]
    with open(file.file.path, 'rb') as pdf:
        response = HttpResponse(pdf.read(), content_type='application/pdf')
        response['Content-Disposition'] = 'attachment;filename=filename=%s'%(filename)
        return response
```

You can replace `` attachment`` with `` inline`` to download emidiatly.
