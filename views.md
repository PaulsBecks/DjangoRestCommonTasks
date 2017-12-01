# ModelViewSet

``` python
from rest_framework import viewsets

class MyModelViewSet(viewsets.ModelViewSet):
    serializer_class = MyModelSerializer
    queryset = MyModel.objects.all()
    
```
