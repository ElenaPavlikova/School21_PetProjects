## Попарное тестирование страницы авторизации <https://www.saucedemo.com>
*выполнено 15.08.2023*  
<table>
  <tr>  
    <th>ID тест-кейса</th>
    <th>Заголовок</th>
    <th>Предшествующие условия</th>
    <th><center>Шаги</center></th>
    <th>Ожидаемый результат</th>
  </tr>
  <tr>
<td>TC 01</td>
<td>Авторизация пользователя "standard_user" с верным паролем</td>
<td>Открыта страница авторизации <https://www.saucedemo.com></td>
<td>

1. В поле "Username" ввести "standard_user"
2. В поле "Password" ввести "secret_sauce"
3. Нажать кнопку "Login"

</td>
<td>Пользователь авторизован</td>
<tr>
<td>TC 02</td><td>Авторизация пользователя "locked_out_user" с верным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "locked_out_user"
2. В поле "Password" ввести "secret_sauce"
3. Нажать кнопку "Login"

</td>
  <td>Пользователь не авторизован</td>
  <tr>

<td>TC 03</td>
    <td>Авторизация пользователя "problem_user" с верным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "problem_user"
2. В поле "Password" ввести "secret_sauce"
3. Нажата кнопка "Login"

</td>
  <td>Пользователь авторизован, на странице каталога баги</td>
  <tr>

<td>TC 04</td>
    <td>Авторизация пользователя "performance_glitch_user" с верным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "performance_glitch_user"
2. В поле "Password" ввести "secret_sauce"
3. Нажать кнопку "Login"

</td>
  <td>Пользователь авторизован с задержкой 6 секунд</td>
  <tr>

<td>TC 05</td>
    <td>Авторизация пользователя "standard_user" с неверным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "standard_user"
2. В поле "Password"  ввести любое значение, кроме верного "secret_sauce"
3. Нажата кнопка "Login"

</td>
  <td>Отображается ошибка входа, Username and password do not match any user in this service</td>
  <tr>

<td>TC 06</td>
    <td>Авторизация пользователя "locked_out_user" с неверным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "locked_out_user"
2. В поле "Password"  ввести любое значение, кроме верного "secret_sauce"
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа, Username and password do not match any user in this service</td>
  <tr>

<td>TC 07</td>
    <td>Авторизация пользователя "problem_user" с неверным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "problem_user"
2. В поле "Password"  ввести любое значение, кроме верного "secret_sauce"
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа, Username and password do not match any user in this service</td>
  <tr>

<td>TC 08</td>
    <td>Авторизация пользователя "performance_glitch_user" с неверным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "performance_glitch_user"
2. В поле "Password"  ввести любое значение, кроме верного "secret_sauce"
3. Нажата кнопка "Login"

</td>
  <td>Отображается ошибка входа, Username and password do not match any user in this service</td>
  <tr>

<td>TC 09</td>
    <td>Авторизация пользователя "standard_user" с незаполненным полем пароля</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "standard_user"
2. Поле "Password" оставить пустым
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа,  Password is required</td>
  <tr>

<td>TC 10</td>
    <td>Авторизация пользователя "locked_out_user" с незаполненным полем пароля</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "locked_out_user"
2. Поле "Password" оставить пустым
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа,  Password is required</td>
  <tr>

<td>TC 11</td>
    <td>Авторизация пользователя "problem_user" с незаполненным полем пароля</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "problem_user"
2. Поле "Password" оставить пустым
3. Нажать кнопку Login

</td>
  <td>Отображается ошибка входа,  Password is required</td>
  <tr>

<td>TC 12</td>
    <td>Авторизация пользователя "performance_glitch_user" с незаполненным полем пароля</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести "performance_glitch_user"
2. Поле "Password" оставить пустым
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа,  Password is required</td>
  <tr>

<td>TC 13</td>
  <td>Авторизация пользователя с неверным логином и верным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести любое значение, кроме верного
2. В поле "Password" ввести "secret_sauce"
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа, Username and password do not match any user in this service</td>
  <tr> 

<td>TC 14</td>
    <td>Авторизация пользователя с неверным логином и с неверным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести любое значение, кроме верного
2. В поле "Password"  ввести любое значение, кроме верного
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа, Username and password do not match any user in this service</td>
  <tr>

<td>TC 15</td>
    <td>Авторизация пользователя с неверным логином и с незаполненным полем пароля</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. В поле "Username" ввести любое значение, кроме верного
2. Поле "Password" оставить пустым
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа,  Password is required</td>
  <tr>

<td>TC 16</td>
    <td>Авторизация пользователя с незаполненным полем логина и верным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. Поле "Username" оставить пустым
2. В поле "Password" ввести "secret_sauce"
3. Нажать кнопка "Login"

</td>
  <td>Отображается ошибка входа, Username is required</td>
  <tr>   

<td>TC 17</td>
    <td>Авторизация пользователя с незаполненным полем логина и неверным паролем</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. Поле "Username" оставить пустым
2. В поле "Password"  ввести любое значение, кроме верного
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа, Username is required</td>
  <tr>

<td>TC 18</td>
    <td>Авторизация пользователя с незаполненным полем логина и незаполненным полем пароля</td>
    <td>Открыта страница авторизации <https://www.saucedemo.com></td>
  <td>

1. Поле "Username" оставить пустым
2. Поле "Password" оставить пустым
3. Нажать кнопку "Login"

</td>
  <td>Отображается ошибка входа, Username is required</td>
  <tr>
</table>
