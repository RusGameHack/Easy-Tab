In English:
This repository will help beginners create simple tabs. We will analyze which line is responsible for what and you will be able to repeat them without problems.

The principle of operation of this headquarters:
We have:
1. 'info-header-tab' - headers that we use to switch tabs
2. 'info-header' - parent block of headers located above
3. 'info-tabcontent' - a block with information that we will switch

Let's look at which line is responsible for what
After we got the variables, we have a function with a loop

function hideTabContent(a) {

        for (let i = a; i < tabContent.length; i++){
        
                tabContent[i].classList.remove('show');//Removing the class that will show the content of all blocks
                
                tabContent[i].classList.add('hide');//Adding a class that hides the content of all blocks
        
        }

}

hideTabContent(1); //Starting with block number 1 to hide all blocks except [0], because we are creating a array tabContent

function showTabContent(b) { 
    
    if(tabContent[b].classList.contains('hide')){ // Here we are checking the block whose content we want to show. If we find the hide class in the block that needs to be shown, then we delete it
    
        tabContent[b].classList.remove('hide');
        
        tabContent[b].classList.add('show');
    
    }

}

info.addEventListener('click', function(event){//Button click event

        let target = event.target;
    
        if (target && target.classList.contains('info-header-tab')){
        
                for(let i = 0; i < tab.length; i++){
            
                        if (target == tab[i]){ //Here is the principle: when we click, we get target (the number of the clicked element) and if target matches the number of the button, then we remove the active element and assign the show class to the block that we need
                
                                hideTabContent(0);
                
                                showTabContent(i);
                
                                break;
            
                        }
        
                }
    
        }

});

That's it! I hope my script will help you!

============================================================

На русском:
Этот репозиторий поможет создать новичкам  простые табы. Мы разберем какая строка за что отвечает и вы сможете повторить их без проблем.

Принцип работы этого таба:
У нас есть: 
1. 'info-header-tab' - заголовки, которые мы использует для переключения табов
2. 'info-header' - родительский блок заголовков, расположенных выше
3. 'info-tabcontent' - блок с информацией, который мы будем переключать

Давайте разберем какая строка за что отвечает
После того, как мы получили переменные, у нас идет функция с циклом
function hideTabContent(a) {
        for (let i = a; i < tabContent.length; i++){
            tabContent[i].classList.remove('show');//Удаляем класс, который будет показывать контент у всех блоков
            tabContent[i].classList.add('hide');//Добавляем класс, скрывающий контент у всех блоков
        }
    }
hideTabContent(1); //Начинаем с блока под номером 1, чтобы скрыть все блоки, кроме [0], потому что мы создаем псевдомассив tabContent

function showTabContent(b) { 
    if(tabContent[b].classList.contains('hide')){ // Здесь мы проводим проверку у блока, контент которого хотим показать. Если находим класс hide у блока, который нужно показать, то мы его удаляем
        tabContent[b].classList.remove('hide');
        tabContent[b].classList.add('show');
    }
}
info.addEventListener('click', function(event){//Событие клик на кнопку
    let target = event.target;
    if (target && target.classList.contains('info-header-tab')){
        for(let i = 0; i < tab.length; i++){
            if (target == tab[i]){ //Здесь принцип такой: при клике мы получаем target(номер элемента, на который кликнули) и если target совпадает с номером кнопки, то мы убираем активный элемент и назначаем класс show тому блоку, который нам нужен
                hideTabContent(0);
                showTabContent(i);
                break;
            }
        }
    }
});

Вот и все! Надеюсь, вам поможет мой скрипт!
