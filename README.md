## Оглавление
**[Концепция работы с двумя конфигурациями](https://github.com/prog185/vinograd#%D0%BA%D0%BE%D0%BD%D1%86%D0%B5%D0%BF%D1%86%D0%B8%D1%8F-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-%D1%81-%D0%B4%D0%B2%D1%83%D0%BC%D1%8F-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B3%D1%83%D1%80%D0%B0%D1%86%D0%B8%D1%8F%D0%BC%D0%B8)**

**[Общая информация по обмену данными](https://github.com/prog185/vinograd#%D0%BE%D0%B1%D1%89%D0%B0%D1%8F-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BE%D0%B1%D0%BC%D0%B5%D0%BD%D1%83-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8)**

**[Перенос данных из Бухгалтерию в Розницу](https://github.com/prog185/vinograd#%D0%BF%D0%B5%D1%80%D0%B5%D0%BD%D0%BE%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%B7-%D0%B1%D1%83%D1%85%D0%B3%D0%B0%D0%BB%D1%82%D0%B5%D1%80%D0%B8%D1%8E-%D0%B2-%D1%80%D0%BE%D0%B7%D0%BD%D0%B8%D1%86%D1%83)**

[Первоначальный перенос. Выгрузка из Бухгалтерии](https://github.com/prog185/vinograd#%D0%BF%D0%B5%D1%80%D0%B2%D0%BE%D0%BD%D0%B0%D1%87%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D0%BF%D0%B5%D1%80%D0%B5%D0%BD%D0%BE%D1%81-%D0%B2%D1%8B%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B8%D0%B7-%D0%B1%D1%83%D1%85%D0%B3%D0%B0%D0%BB%D1%82%D0%B5%D1%80%D0%B8%D0%B8)

[Регулярный перенос. Выгрузка из Бухгалтерии](https://github.com/prog185/vinograd#%D1%80%D0%B5%D0%B3%D1%83%D0%BB%D1%8F%D1%80%D0%BD%D1%8B%D0%B9-%D0%BF%D0%B5%D1%80%D0%B5%D0%BD%D0%BE%D1%81-%D0%B2%D1%8B%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B8%D0%B7-%D0%B1%D1%83%D1%85%D0%B3%D0%B0%D0%BB%D1%82%D0%B5%D1%80%D0%B8%D0%B8)

[Загрузка в Розницу](https://github.com/prog185/vinograd#%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B2-%D1%80%D0%BE%D0%B7%D0%BD%D0%B8%D1%86%D1%83)

**[Перенос данных из Розницы в Бухгалтерию](https://github.com/prog185/vinograd#%D0%BF%D0%B5%D1%80%D0%B5%D0%BD%D0%BE%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%B7-%D1%80%D0%BE%D0%B7%D0%BD%D0%B8%D1%86%D1%8B-%D0%B2-%D0%B1%D1%83%D1%85%D0%B3%D0%B0%D0%BB%D1%82%D0%B5%D1%80%D0%B8%D1%8E)**

[Выгрузка из Розницы](https://github.com/prog185/vinograd#%D0%B2%D1%8B%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B8%D0%B7-%D1%80%D0%BE%D0%B7%D0%BD%D0%B8%D1%86%D1%8B)

[Загрузка в Бухгалтерию](https://github.com/prog185/vinograd#%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B2-%D0%B1%D1%83%D1%85%D0%B3%D0%B0%D0%BB%D1%82%D0%B5%D1%80%D0%B8%D1%8E)

## Концепция работы с двумя конфигурациями
### Предварительные ласки
1. Из **Бухгалтерии предприятия** в **Розницу** производится первоначальная выгрузка необходимой нормативно-справочной информации: справочников номенклатуры, контрагентов, организаций, складов и т.д.
1. Перенос "входящих остатков": в **Бухгалтерии предприятия** создается документ **Поступление товаров и услуг**, содержащий весь товар, имеющийся в наличии на складе. Далее данный документ переносится в **Розницу**. Это необходимо для того, чтобы оприходовать в **Рознице** товар, уже имеющийся на складе, чтобы программа в дальнейшем дала его продать. После оприходования товара в **Рознице** данный документ в **Бухгалтерии предприятия** можно удалить (пометить на удаление).
### Регулярный обмен
1. При создании в **Бухгалтерии предприятия** документов **Поступление товаров и услуг** они будут переноситься в **Розницу**.  
1. При создании в **Рознице** документов **Реализация товаров** они будут переноситься в **Бухгалтерию предприятия**.
1. Как правило, обмен документами производится ежедневно, в конце рабочего дня (или после того, как созданы все документы за текущий день). 
1. В случае необходимости, любой документ можно перенести в другую базу в любое время непосредственно после его создания.
1. Если появится необходимость добавить в **Рознице** новую номенклатурную позицию, нового контрагента, склад и т.п., то сначала надо это сделать в **Бухгалтерии**. После того, как элемент будет заведен в бухгалтерской базе, его можно нужно перенести в розницу так же, как осуществлялся первоначальный перенос.

## Общая информация по обмену данными

1. Правила обмена данными создавались в конфигурации **Конвертация данных 2.1.8.2**. Обмен данными между конфигурациями **Бухгалтерия предприятия** и **Розница** является актуальным для следующих версий/релизов:
   
    1. **Бухгалтерия предприятия** - 2.0.66.63
    1. **Розница** - 2.2.0.19
1. Обмен данными будет производиться путем выгрузки необходимых объектов (справочников, документов и т.д.) в файл \*.xml из конфигурации-источника и загрузки этого файла в конфигурацию-приемник.
1. Выгрузка и загрузка данных производится с помощью обработки **Универсальный обмен данными в формате XML**. В **Бухгалтерии предприятия** для этого будет использоваться внешняя обработка из файла **V8Exchan82.epf**, в **Рознице** - встроенная обработка **Универсальный обмен данными в формате XML**
1. Для того, чтобы выгрузить нужные данные, в обработке **Универсальный обмен данными...** необходимо указывать правильный **файл с правилами обмена**!
1. При обновлении какой-либо конфигурации существет риск, что обновление затронет один из переносимых объектов! Поэтому после обновления программ необходимо проверить корректность работы обмена и при необходимости внести правки в файлы с правилами обмена.

## Перенос данных из Бухгалтерию в Розницу
### Первоначальный перенос. Выгрузка из Бухгалтерии
1. Скачать файл обработки обмена данными **V8Exchan82.epf** и файл с правилами обмена **ПравилаОбменаДанными_Справочники.xml**
1. Открыть файл **V8Exchan82.epf** в **Бухгалтерии предприятия** (через пункты меню "Файл"->"Открыть").
1. На вкладке **Выгрузка данных** заполнить следующие поля:
   
    1. **Имя файла правил** - скачанный файл **ПравилаОбменаДанными_Справочники.xml**. На вопрос "Загрузить правила обмена данными?" ответить положительно. После этого будет заполнена табличная часть, содержащая правила выгрузки данных.
    1. Проставить переключатель в значение **Выгрузка в файл обмена**.
    1. **Имя файла данных** - указать файл, в который будет производиться выгрузка:  
![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_01.png)
1. Нажать на кнопку "Выгрузить данные". Будет произведена выгрузка данных в файл, указанный в поле "Имя файла данных". По окончанию выгрузки система оповестит об этом в служебных сообщениях:

![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_02.png)

### Регулярный перенос. Выгрузка из Бухгалтерии
1. Открыть файл **V8Exchan82.epf** в **Бухгалтерии предприятия** (через пункты меню "Файл"->"Открыть").
1. На вкладке **Выгрузка данных** заполнить следующие поля:
   
    1. **Имя файла правил** - скачанный файл **ПравилаОбменаДанными_Бух-Розница.xml**. На вопрос "Загрузить правила обмена данными?" ответить положительно. После этого будет заполнена табличная часть, содержащая правила выгрузки данных.
    1. Проставить переключатель в значение **Выгрузка в файл обмена**.
    1. **Имя файла данных** - указать файл, в который будет производиться выгрузка:  
![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_12.png)
1. Нажать на кнопку "Выгрузить данные". Будет произведена выгрузка данных в файл, указанный в поле "Имя файла данных". По окончанию выгрузки система оповестит об этом в служебных сообщениях:

![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_02.png)
### Загрузка в Розницу
1. Убедиться, что присутствует пункт меню **Все Функции**:

![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_03.png)

2. Если его нет - необходимо включить его отображение в параметрах (**Сервис** -> **Параметры**):

![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_04.png)

3. Открыть обработку **Универсальный обмен данными в формате XML**: **Все функции* -> **Обработки** -> **Универсальный обмен данными в формате XML**:

![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_05.png)

4. Перейти на вкладку **Загрузка данных** и заполнить следующие поля:
   
    1. **Имя файла для загрузки на сервере** - здесь надо указать файл с выгруженными данными. Это тот файл, который указывался при выгрузке в поле **Имя файла данных**.
    1. Проставить остальные флажки и переключатели так, как указано ниже:
    
![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_06.png)

5. Нажать на кнопку **Загрузить данные**. По окончанию загрузки система оповестит об этом в служебных сообщениях:

![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_07.png)


## Перенос данных из Розницы в Бухгалтерию
### Выгрузка из Розницы
1. Скачать файл с правилами обмена **ПравилаОбменаДанными_Розница_Бух.xml**
1. Открыть обработку **Универсальный обмен данными в формате XML**: **Все функции* -> **Обработки** -> **Универсальный обмен данными в формате XML**. 
1. Перейти на вкладку **Выгрузка данных** и заполнить следующие поля:

    1. **Имя файла правил на сервере** - указать скачанный файл с правилами файл **ПравилаОбменаДанными_Розница_Бух.xml**.
    1. **Имя файла данных на сервере** - указать файл, в который будет производиться собственно выгрузка даных в Буугатерию.
    1. Проставить остальные флажки и переключатели так, как указано ниже:
    
![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_08.png)

4. Нажать на кнопку **Выгрузить данные**. Будет произведена выгрузка данных. По окончанию выгрузки система оповестит об этом в служебных сообщениях:

![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_09.png)

### Загрузка в Бухгалтерию
1. Открыть файл **V8Exchan82.epf** в **Бухгалтерии предприятия** (через пункты меню "Файл"->"Открыть").
1. Перейти на вкладку **Загрузка данных** и заполнить следующие поля:
   
    1. **Имя файла для загрузки** - указать файл с выгруженными из **Розницы** данными. Это файл, который указывался при выгрузке з Розницы в поле **Имя файла данных на сервере**.
    1. Проставить остальные флажки и переключатели так, как указано ниже:
    
![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_10.png)

3. Нажать на кнопку "Загрузить данные". Будет произведена загрузка данных. По окончанию загрузки система оповестит об этом в служебных сообщениях:

![](https://github.com/prog185/vinograd/blob/other/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD_11.png)
