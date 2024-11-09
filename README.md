# Домашнее задание к занятию «Базовые объекты K8S»- Михалёв Сергей

### Цель задания

В тестовой среде для работы с Kubernetes, установленной в предыдущем ДЗ, необходимо развернуть Pod с приложением и подключиться к нему со своего локального компьютера. 

------

### Чеклист готовности к домашнему заданию

1. Установленное k8s-решение (например, MicroK8S).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключенным Git-репозиторием.

------

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. Описание [Pod](https://kubernetes.io/docs/concepts/workloads/pods/) и примеры манифестов.
2. Описание [Service](https://kubernetes.io/docs/concepts/services-networking/service/).

------

### Задание 1. Создать Pod с именем hello-world

1. Создать манифест (yaml-конфигурацию) Pod.
2. Использовать image - gcr.io/kubernetes-e2e-test-images/echoserver:2.2.
3. Подключиться локально к Pod с помощью `kubectl port-forward` и вывести значение (curl или в браузере).

**Решение**

Создал манифест [hello-world-pod.yaml](manifests/hello-world-pod.yaml). Запустил командой `microk8s kubectl apply -f hello-world-pod.yaml`</br>
Проверил список подов.</br>
<img src="images/Task_1_1.png" alt="Task_1_1.png" width="300" height="auto"></br>
Проверил работу nginx через браузер.</br>
<img src="images/Task_1_2.png" alt="Task_1_2.png" width="500" height="auto"></br>





------

### Задание 2. Создать Service и подключить его к Pod

1. Создать Pod с именем netology-web.
2. Использовать image — gcr.io/kubernetes-e2e-test-images/echoserver:2.2.
3. Создать Service с именем netology-svc и подключить к netology-web.
4. Подключиться локально к Service с помощью `kubectl port-forward` и вывести значение (curl или в браузере).

**Решение**

Создал манифест [netology-web.yaml](manifests/netology-web.yaml)</br>
Проверил список подов.</br>
<img src="images/Task_2_1.png" alt="Task_2_1.png" width="350" height="auto"></br>


Создал манифест [netology-svc.yaml](manifests/netology-svc.yaml)</br>
Проверил список сервисов.</br>
<img src="images/Task_2_2.png" alt="Task_2_2.png" width="400" height="auto"></brhell  

Проверил подключение через curl</br>
<img src="images/Task_2_3.png" alt="Task_2_3.png" width="300" height="auto"></brhell

Проверил в браузере</br>
<img src="images/Task_2_3.png" alt="Task_2_3.png" width="300" height="auto"></brhell

------

### Правила приёма работы

1. Домашняя работа оформляется в своем Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода команд `kubectl get pods`, а также скриншот результата подключения.
3. Репозиторий должен содержать файлы манифестов и ссылки на них в файле README.md.

------

### Критерии оценки
Зачёт — выполнены все задания, ответы даны в развернутой форме, приложены соответствующие скриншоты и файлы проекта, в выполненных заданиях нет противоречий и нарушения логики.

На доработку — задание выполнено частично или не выполнено, в логике выполнения заданий есть противоречия, существенные недостатки.
