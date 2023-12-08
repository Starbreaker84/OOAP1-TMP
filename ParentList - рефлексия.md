## Рефлексия:
Ход проектирования был, в принципе, понятен. И напутать тут было бы сложно. Предусловия и постусловия совпали, что ожидаемо, поскольку было все разложено по полочкам на предыдущем занятии. По ощущениям, такой подход начал хорошо дисциплинировать. Переношу частично на рабочие процессы и результат нравится. Правда, в рабочих вариантах не использую статусы пока, коллеги не понимают.
Уже после реализации замети, что ни у меня, ни в эталонном решении как-будто бы нет вариантов корректной вставки элемента, надо будет с этим разобраться.

## Эталонное решение:
```
abstract class ParentList<T>

  // конструктор
  public ParentList<T> ParentList();

  // команды
  public void head(); 
  public void tail(); 
  public void right(); 
  public void put_right(T value); 
  public void put_left(T value); 
  public void remove();
  public void clear(); 
  public void add_tail(T value); 
  public void remove_all(T value);
  public void replace(T value); 
  public void find(T value); 

  // запросы
  public T get();
  public bool is_head();
  public bool is_tail();
  public bool is_value();
  public int size();

  // запросы статусов
  public int get_head_status();
  public int get_tail_status();
  public int get_right_status();
  public int get_put_right_status();
  public int get_put_left_status();
  public int get_remove_status();
  public int get_replace_status();
  public int get_find_status();
  public int get_get_status();

abstract class LinkedList<T> : ParentList<T>

  // конструктор
  public LinkedList<T> LinkedList();

abstract class TwoWayList<T> : ParentList<T>

  // конструктор
  public TwoWayList<T> TwoWayList();

// предусловие: левее курсора есть элемент; 
// постусловие: курсор сдвинут на один узел влево
  public void left();

  public int get_left_status(); // успешно; левее нету элемента
```
