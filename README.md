Replacement buttons to cart (Замена кнопки в корзину)
=============

Даний модуль дозволяє замінити кнопку "В корзину" на "В корзине" коли товар додано в корзину магазину. Працює на OpenCart 2.* з шаблоном Journal 2.


Installation
-----------
1 - Відкрити файл journal.js який знаходить в catalog/view/theme/journal2/js

2 - Далі знайти та додати кілька кусків коду:

- *Знайти (майже в самому кінці файлу)*
`$(document).ready(function(){`та додати нижче нову стрічку `ProductList_array();`

- *Знайти* `function addToCart(product_id, quantity) {` та додати нижче нову стрічку `replace_button(product_id);`

- *Знайти* `cart.remove = function(key) {` та замінити стрічку на `cart.remove = function(product_id, key) {`

- *Знайти* `if (getURLVar('route') == 'checkout/cart' || getURLVar('route') == 'checkout/checkout') {` та додати над нею нову стрічку `return_button(product_id);`

3 - Встановити OCMOD replacebc.ocmod.xml через менеджер розширень. Не забуваємо натиснути на кнопку `Оновити` - щоб оновити Кеш!

4 - Приємного користування.



<!--
<file path="catalog/view/theme/journal2/js/journal.js">
	<operation>
	<search><![CDATA[$(document).ready(function(){]]></search>
	<add position="after"><![CDATA[
		ProductList_array();
	]]></add>
	</operation>
    
  	<operation>
	<search><![CDATA[function addToCart(product_id, quantity) {]]></search>
	<add position="after"><![CDATA[
		replace_button(product_id);
	]]></add>
	</operation>
    
    <operation>
	<search><![CDATA[cart.remove = function(key) {]]></search>
	<add position="replace"><![CDATA[
		cart.remove = function(product_id, key) {
	]]></add>
	</operation>
    
    <operation>
	<search><![CDATA[if (getURLVar('route') == 'checkout/cart' || getURLVar('route') == 'checkout/checkout') {]]></search>
	<add position="before"><![CDATA[
		return_button(product_id);
	]]></add>
	</operation>
</file>
-->

-------
Автор: Павло Глухинчук

Email: dj_pasha@bk.ru

Site: http://hlam.org.ua
