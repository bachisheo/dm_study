 # Метод математической индукции. Аксиомы индукции. Индукция на графах. Примеры.
Индукцией называют переход от частных утверждений к общим.  

### **Принцип полной индукции.**
Пусть P — утверждение относительно натуральных чисел n, такое что:
1. P верно для n = 0;
2. из справедливости P для n = k следует справедливость P для n = k + 1.  

Тогда P верно для всех натуральных чисел.

Другая форма принципа полной индукции:  
Пусть P — утверждение относительно натуральных чисел n, такое что:
1. P верно для $n$ = $n_0$;
2. из справедливости P для $n = n_0, n_0 + 1,  ..., n_0+k$ следует справедливость P для $n = n_0+k+1$.  

Тогда P верно для всех $n \ge n_0$. 

### **Метод математической индукции**
**Метод мат индукции** основывается на принципе индукции и состоит из следующих этапов: 
1. Проверяем истинность утверждения при n = 1 (база индукции);
2. Предполагаем, что утверждение верно при произвольном натуральном n = k (предположение индукции);
3. Доказываем истинность утверждения для натурального n = k + 1,
исходя из предположения индукции (пункт 2) (шаг индукции).


# Индукция на графах.
Мб по числу вершин или ребер

Как сделать шаг индукции?  
Пусть у насть множество графов $A_n$ и $A_{n+1}$ с $n$ и $n+1$ вершинами, для $A_n$ есть предположение индукции. Если мы будем делать шаг индукции, добавляя к любому графу из $A_n$ одну вершину с некоторыми ребрами, то мы можем не получить все графы из $A_{n+1}$.  
Поэтому мы должны брать граф из $A_{n+1}$ и удалять любую вершину из него, тем самым получая граф из $A_n$, для которого имеется предположение индукции.

# Аксиомы индукции (????) 
**Аксиома индукции**: единственное подмножество множества N, которое, во-первых, содержит 0 и, во-вторых, вместе с каждым элементом x содержит непосредственно следующий за ним элемент s(x), — это само множество N.

**Принцип наименьшего числа** (равносильно тому, что выше)   
Каждое непустое подмножество множества натуральных чисел содержит наименьший элемент (т.е. элемент, который не следует ни за одним элементом этого множества).

**Аксиома Пеано** 
Если какое-либо предложение доказано для 0 (база индукции) и если из допущения, что оно верно для натурального числа n, вытекает, что оно верно для следующего за n натурального числа (индукционное предположение), то это предложение верно для всех натуральных чисел
