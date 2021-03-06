# project-python3

Общее описание проекта.  
Проект представляет собой графиеский редактор, открывающийся в отдельном окне.  
При запуске пользователь увидит пустое окно, с кнопками сверху, одной из которых будет загрузка фотографии.  
После выбора изображения, оно показывается на экране, где мы будем видить результаты редактирования, всего кнопок восемь:  
  • New - создаётся новый проект, предлагается выбрать фотографию для редактирования  
  • Save - сохраняет изображение в текущей директории  
  • Save As - сохраняет в выбранной пользователем директории  
  • Draw - рисование  
  • Crop - обрезает по контуру  
  • Filter - при нажатии всплывает окно с шестью эффектами, которые можно наложить на изображение, а именно: Negative, Black White, Sepia, Emboss, Guassian Blur, Median Blur  
  • Adjust - при нажатии всплывают четыре ползунка, каждый из которых меняет: Brightness - яркость изображения, R - красный цвет, G - зелёный цвет, B - синий цвет  
  • Clear - очищает все изменения, возвращает изображение к исходному состоянию  
  
  
Пройдемся по частям кода.  

- Модуль init.  
Объявляем и фиксируем главное окно.

- Модуль main.  
Изображение в программе представляется объектом класса со своим списком параметров (название, оригинал, копия, выбрано ли оно, рисуем ли что-то, вырезаем ли что-то, примененный фильтр, регулировка фильтра).  
Дальше мы строим интерфейс (кнопки, линию и рабочее окно).

- Модуль editBar.  
Создаем кнопки, связываем их с функциями, размещаем на окне. Дальше прописаны функции кнопок. Перед запуском проверяется выбрана ли фотография, если да, то рисуем ли что-то или вырезаем, если да, но прекращаем процессы.  

- Модуль imageViewer.  
Модуль показывает изображение, позволяет рисовать и вырезать куски.
Переменные состояния: выбранное изображение, его координаты начала, координаты начала и конца вырезаемой части, список раскрашенных пикселей, отношение сторон исходного изображения.  

- Модуль filterFrame.  
Создаем кнопки, связываем их с функциями, размещаем на окне. Дальше прописаны функции кнопок. Перед запуском проверяется выбрана ли фотография, если да, то рисуем ли что-то или вырезаем, если да, но прекращаем процессы.  
Ссылка на функцию sepia: https://stackoverflow.com/questions/59880704/how-can-i-check-if-an-image-is-sepia/59903481#59903481  

- Модуль adjustFrame.  
Создаем новое окно, создаем и размещаем надписи (яркость, rgb), создаем и размещаем горизонтальные бегунки, задаем их диапозонвы, по которым будем брать коэффициент. Прописываем функции применить, показать, закрыть, отменить.
