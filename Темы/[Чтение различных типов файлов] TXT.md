
![[Pasted image 20241010110158.png]]
## Чтение текстового файла полностью

```js
Текст = Новый ТекстовыйДокумент;
Текст.Прочитать(Объект.ПутьКФайлу, КодировкаТекста.ANSI);

Для НомерСтроки = 1 По Текст.КоличествоСтрок() Цикл
	СтрокаТекста = Текст.ПолучитьСтроку(НомерСтроки);
	ДобавлениеЭлементаВТаблицуПоСтроке(СтрокаТекста);			
КонецЦикла;
```

## Чтение текстового файла построчно

```js
Текст = Новый ЧтениеТекста(Объект.ПутьКФайлу, КодировкаТекста.ANSI);
Стр = Текст.ПрочитатьСтроку();

Пока Стр <> Неопределено Цикл
	ДобавлениеЭлементаВТаблицуПоСтроке(Стр);
	Стр = Текст.ПрочитатьСтроку();
КонецЦикла;
```

## Добавление Элемента В Таблицу По Строке

```js
&НаКлиенте
Процедура ДобавлениеЭлементаВТаблицуПоСтроке(Строка)
	
	МассивСтрок = СтрРазделить(Строка, ";");
	
	Если МассивСтрок.Количество() < 3 Тогда
		Возврат;		
	КонецЕсли;
	
	НоваяСтрока = Объект.ТаблицаДанных.Добавить();
	НоваяСтрока.Наименование = МассивСтрок[0];
	НоваяСтрока.ПолноеНаименование = МассивСтрок[1];
	НоваяСтрока.УНП = МассивСтрок[2];
	
КонецПроцедуры // ()
```









