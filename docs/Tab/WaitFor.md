---
layout: docsMember
permalink: /docs/Tab/WaitFor

categories:
    - Методы расширения Tab

title:          WaitFor
member:
    type:       method
    name:       WaitFor(System.Func{System.Boolean} predicate,System.Int32 timeout)
    summary:    'Выполняет ожидание, пока предикат не вернет true, либо до истечения таймаута.'
    returns:    'Тот же объект <see cref="T:ZennoLab.CommandCenter.Tab" />для Fluent Interface'
    params:
        - name:  predicate
          value: 'Условное выражение.'
        - name:  timeout
          value: 'Длительность проверки выражения в миллисекундах. По умолчанию 5000.'

---

