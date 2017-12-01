---
layout: docsMember
permalink: docs/MultiLogger/GetInstance/

categories:
    - Мультилогер

title:          GetInstance
member:
    type:       method
    name:       GetInstance(ZennoLab.InterfacesLibrary.ProjectModel.IZennoPosterProjectModel project)
    summary:    'Возвращает экземпляр класса MultiLogger.'
    returns:    'Экземпляр MultiLogger.'
    params:
        - name:  project
          value: 'Экземпляр project.'

---

```csharp
var logger = MultiLogger.GetInstance(project);
```
