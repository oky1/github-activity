# Fork of GitHub Activity Stream Widget


Данный модуль является форком [данного модуля](https://github.com/caseyscarborough/github-activity). Наш модуль может отражать активность не только
какого-то одного аккаунта или репозитория, а позволяет выводить на экран неограниченное их количество. Далее приводим текст установки  модуля: 


Для начала необходимо скачать архив с github: https://github.com/diglabby/github-activity/archive/master.zip После этого содержимое папки github-activity внутри архива необходимо распокавать в корень папки вашего сайта. Следом подключаем необходимые файлы в хэдере вашего html-файла:


```
<head>
<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/octicons/2.0.2/octicons.min.css">
<link rel="stylesheet" href="src/github-activity.css">

<script src="//code.jquery.com/jquery-1.11.0.js"></script>
<script type="text/javascript" src="//cdnjs.cloudflare.com/ajax/libs/mustache.js/0.7.2/mustache.min.js"></script>
<script type="text/javascript" src="src/github-activity.js"></script>
<script>
</head>

```
## 
После внутри body своего html-файл мы создаем объект нашего модуля, внутри которого мы вводим конфигурационные данные таким манером:
```
GitHubActivity.feed({
	username: "diglabby", // optional
  handler: "handler.php", // optional
  repositories: {
  diglabby:["b-prylady","liga"],
  MrKarlKori:"MrKarlKori",
	
	selector: "#feed",
	limit: 20 // optional
  
});

```
## Возможны два варианта использования модуля:
1) Оригинальная функциональность. Для ее достижение мы не указываем свойства handler и repositories. Модуль будет отображать только активность одного пользователя указанного в свойстве username или активность одного репозитория, указанного в  свойстве repository. 
2) Отображение активности множества разных репозиториев или юзеров. Для этого 
   a)В поле username указываем ник пользователя, сведения о котором будут показываться в шапке модуля. 
   б) В свойстве handler мы указываем путь до файла handler.php, который  распакован и находится тут же в корневой папке Вашего сайта. 
   в) В свойстве repositories указывается объект, хранящий список пользователей и отдельных репозиториев, которые необходимо отобразить в модуле гит-хаб активности. 
   Список указывается следующим образом: 
   а) Для добавления всей активности конкретного пользователя, создаётся ключ в виде имени пользователя, которому строкой присвоено значение в виде этого же имени:
   ```
   MrKarlKori:"MrKarlKori"
   
   ```
   
   
   б) Для добавления активности избранных репозиториев одного пользователя, создаётся ключ в виде имени пользователя, хранящего значение в виде массива, каждый элемент которого является именем нужного репозитория.
```js
  user:["repository1","repository2"],
```
  В общем виде это выглядит так:
```
repositories: {
  user:["repository1","repository2"],
  MrKarlKori:"MrKarlKori"
  }
  
```
   

## Комментарии и форки приветствуются.
