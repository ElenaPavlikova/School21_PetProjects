### Интуитивное тестирование <http://testingchallenges.thetestingmap.org/login/login.php> при наличии требований:

- Корректными данными для авторизации являются: *username — admin, password — admin*;
- В форме авторизации выводится сообщение *Logged In Successfully* при вводе корректных авторизационных данных;
- В форме авторизации выводится сообщение *Enter Both Username And Password*, если хотя бы одно из полей не заполнено;
- В форме авторизации выводится сообщение *Username Not Found*, если введено любое другое значение *username*;
- В форме авторизации выводится сообщение *Incorrect password*, если введён верный *username* и неверный пароль;
- Все сообщения выводятся над кнопкой *Log In*;
- Форма авторизации предлагает выбрать один из четырёх языков интерфейса: английский, французский, итальянский, немецкий;
- Выбранный язык не сбрасывается после попытки авторизации.

# Баг-репорты

<table border="1">
<thead>
  <tr>
<th>№</th>
<th>Заголовок</th>
<th>Предшествующие условия</th>
<th>Серьезность</th>
<th>Шаги воспроизведения</th>
<th>Ожидаемый результат</th>
<th>Фактический результат</th>
<th>Окружение</th>
</tr>
</thead>
<tbody>
  <tr>
<td>Баг №1</td>
<td>Ввод корректных данных для авторизации</td>
<td>Пользователь находится на странице авторизации</td>
<td>Blocker</td>
<td> 
<ol>
<li>В поле "Username" ввести логин "admin".</li>
<li>В поле "Password" ввести пароль "admin".</li>
<li>Нажать кнопку "Log In".</li>
</ol>
</td>

<td>Появляется сообщение "Logged In Successfully"</td>
<td>Появляется сообщение "Enter Both Username And Password"</td>
<td>ОС Windows 11, браузер Microsoft Edge версия 116.0.1938.54</td>
</tr>
<tr>
<td>Баг №2</td>
<td>Ввод некорректного Username и корректного Password</td>
<td>Пользователь находится на странице авторизации</td>
<td>Blocker</td>
<td>
<ol>
<li>В поле "Username" ввести пароль "Admin"</li>
<li>В поле "Password" ввести пароль "admin".</li>
<li>Нажать кнопку "Log In".</li>
</ol>
</td>
<td>Появляется сообщение "Username Not Found" </td>
<td>Появляется сообщение "Logged In Successfully"</td>
<td>ОС Windows 11, браузер Microsoft Edge версия 116.0.1938.54</td>
 </tr>
 <tr>
  <tr>
<td>Баг №3</td>
<td>Ввод корректного Username и некорректного Password</td>
<td>Пользователь находится на странице авторизации</td>
<td>Blocker</td>
<td>
<ol>
<li>В поле "Username" ввести логин "admin".</li>
<li>В поле "Password" ввести пароль "12345".</li>
<li>Нажать кнопку "Log In".</li>
</ol>
</td>
<td>Сообщение об ошибке Incorrect password </td>
<td>Сообщение Username Not FoundLogged In Successfull</td>
<td>ОС Windows 11, браузер Microsoft Edge версия 116.0.1938.54</td>
 </tr>
<td>Баг №4</td>
<td> Пустые поля "Username" и "Password"
</td>
<td>Пользователь находится на странице авторизации</td>
<td>Blocker</td>
<td>
<ol>
<li>Поля "Username" и "Password" оставить пустыми."</li>
<li>Нажать кнопку "Log In".</li>
</ol>
</td>
<td>Появляется сообщение "Enter Both Username And Password"</td>
<td>Появляется сообщение "Username Not Found"</td>
<td>ОС Windows 11, браузер Microsoft Edge версия 116.0.1938.54</td>
 </tr>
  <tr>
<td>Баг №5</td>
<td>Расположение сообщений системы</td>
<td>Пользователь находится на странице авторизации</td>
<td>Minor</td>
<td>
<ol>
<li>В поле "Username" ввести логин "admin".</li>
<li>Поле "Password" оставить пустым.</li>
<li>Нажать кнопку "Log In".</li>
</ol>
</td>
<td>Сообщение "Enter Both Username And Password" появляется над кнопкой "Log In" </td>
<td>Сообщение "Incorrect password" расположено в верхнем левом углу</td>
<td>ОС Windows 11, браузер Microsoft Edge версия 116.0.1938.54</td>
 </tr>
  <tr>
<td>Баг №6</td>
<td>Выбор нужного языка интерфейса</td>
<td>Пользователь находится на странице авторизации</td>
<td>Major</td>
<td>
<ol>
<li>В поле "Username" ввести логин "admin".</li>
<li>В поле "Password" ввести пароль "admin".</li>
<li>Раскрыть окно выбора языка интерфейса.</li>
</ol>
</td>
<td>Раскрывающееся окно содержит языки: English, Francais, Italiano, Deutsch</td>
<td>Раскрывающееся окно содержит языки: English, Francais, Deutsch, но Italiano отсутствует
</td>
<td>ОС Windows 11, браузер Microsoft Edge версия 116.0.1938.54</td>
 </tr>
  <tr>
<td>Баг №7</td>
<td>Сохранение выбранного языка интерфейса после попытки авторизации</td>
<td>Пользователь находится на странице авторизации</td>
<td>Major</td>
<td>
<ol>
<li>В поле "Username" ввести логин "admin".</li>
<li>В поле "Password" ввести пароль "admin".</li>
<li>Выбрать язык интерфейса - Francais.</li>
<li>Нажать кнопку "Log In"</li>
</ol>
</td>
<td>Сообщение на французском языке "Connexion réussie"</td>
<td>Сообщение на английском языке "Enter Both Username And Password"</td>
<td>ОС Windows 11, браузер Microsoft Edge версия 116.0.1938.54</td>
 </tr>
</thead>
<tbody>
