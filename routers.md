# Routers

[Routers](http://www.django-rest-framework.org/api-guide/routers/) help to create urls for ViewSets.

``` python
router = routers.SimpleRouter()
router.register(r'mymodel', MyModelViewSet)

urlpatterns = [...]

urlpatterns += router.urls
```
