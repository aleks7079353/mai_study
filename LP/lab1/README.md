# ����� �� ������������ ������ �1
## ������ �� �������� � ����������� �������������� ������
## �� ����� "���������� ����������������"

## ��������

����� ������ � ������� ����� ����������� ��� �������� ������, � ������� �������� ��������� �������� ������ ��� ������ ������. ���������� ������ ����� ���� ����� �������. �� ���� �� ���� ����, ���� ������� �� 2� ������: ������ � ������, ������� ��� �������� �������.

��, ��� ���������� ������� � ������������ ������, ������ ���������� �� ������ � �������. �� �� ���� ������������ ������ ���� ����� ��������� ������, ��� ������. ������������ �������� ������ � ������� ����� ������ ����������, �������� ������ �� ������ � �����. � ������������ ������, ����� ���������� � ������-�� �������� ������, �� ����� ������������ ���������. ������ � ������������ ����� ����� ��������� � ���� ������ �������� ���������� ����, � ������� ������ �������� ����� ��������. �������� ���� �� �������� ������ � ������� � ���������, �.�. � ��, � ������ ���� ������ ����� ������������ � ����������. �� � ��������� ������� �� ����� ������������ ������, ���� �� ������� � �������.

����� ����������� ���������� ��������� ������� ������� �� �����, ��� ������ ����� ��������� ��� ������������� ��������, ������ � ��������� ������� ��������� �� �����������, � ��� ������ ������� ����� ��������, ����� ���� ���� � ��� �� ������ ����� ����������� � ������ ��������� ���. 


## ������� 1.1: �������� ��������� ������

`add_last_std(E,L1,L2)` - ��������� ������� � ����� ������ � ������� ����������� ����������
`add_last(E,L1,L2)` - ��������� ������� � ����� ������ ��� ������������� ����������� ����������

������� �������������:
```prolog
| ?- add_last_std(1,[],X).
X = [1]
| ?- add_last_std(1,[2,1,2,1,2],X).
X = [2,1,2,1,2,1]
| ?- add_last(2,[0,0,0],X).
X = [0,0,0,2]
| ?- add_last(5,[1,2,3,4,5,6,7,8,9,10,11,12,13,14],X).
X = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,5]
```

����������:
```prolog
add_last_std(X, L1, L2):-append(L1, [X], L2).
```
� ������� ������������ ��������� append ���������� �������� ������ � ������, ��������� �� ��������, ������� ����� �������� � �����. �.�. ��� ����� �������� � �����, �� �� ����� ������ �� ������ ����� � ��������� append.

```prolog
add_last(X, [], [X]).
add_last(X, [H|T], [H|R]):-add_last(X, T, R).
```
���������� "��������" �������� ������. ����� �� ����, �� �������� ������� � �������������� ������. ��� ������ �� ������� ������������ ����, ��������, ���������� � �������� ������, ������������ ���� ��, � ���� �� ���������� � ������ ��������������� ������.

## ������� 1.2: �������� ��������� ��������� ������

`is_arithm(L)` - ��������� ������ �� �������������� ����������

������� �������������:
```prolog
| ?- is_arithm([1,2,3,4,5]).
yes
| ?- is_arithm([0,10,20,30,40,50]).
yes
| ?- is_arithm([1,3,4,7,10]).
no
| ?- is_arithm([1,3,5,7,9,10]).
no
| ?- is_arithm([1,3,5,7,9,11]).
yes
```

����������:
```prolog
is_arithm([X,Y,Z|T]):-
    !,
    X - Y =:= Y - Z,
    is_arithm([Y,Z|T]).
is_arithm(_).
```
"��������" � ������ ������ 3 ��������. ���������� ���������, ����� ����� �� �������� ��� ��������. ���������� �������� 1��� � 2��� � 2��� � 3��� ���������. ���� ��������� �� �����������, �� ������� �� �������� � ���������. ����� ���������� ������������ ������ ��� 1��� ��������.

## ������� 2: ����������� ������������� ������

����������� ������������� ���������� ��������� ����� ���������, � ������� ������������ �������� ������ ���� ���������. ��������� ������� � ����� ������ -- ��� ��������� �������, ��������������� ���������� ��������� ���������. ��� ������ �������� � ���������� ����� ���������, ������� ��������� ������ �������. ��� ��������� ��������� ��������� �������� ������ �� ������������ � �������. � ���� ������� ����� ��������� � ������������ � ���������, ����� ����� ��������� �� ��� ����������� �������. � ������������� ����� ������� ������������� �������� ����������: ��������� ����������� �� ��������� ����������, ������� ����������� ���������� ���� �� �����. �� ���� � ���� ��������� ��������� �� ����� ����� �����������, ������� ��� ������������ ���������� ���������� ������.

��� ������������� ������� ����� ���������� ��� ������ ����� � ������ ������������ �� ���������. ������� ���������� ������ ������������� � ���, ��� ��� ����� �� ������� ��������� ������ ��������, ������������ ������. � ������ ��������� � ����� ������, �.�. ��� ���������� �� �������. �� ������ ������ ���������� �� ��������, ����� ����� �������� ���������� �� �������. ��������� ���� "������ -- �������" ������ ��������. ��������, ���� �� ������ ��������������� ����������� ����������� assert/asserta/assertz, ��, ��-������, �� ������ �����, ��� ��������� ������ ������ �� ����������� grade, ��-������, ��� ����������� �������� ������, ���, ������, ������������. ����� �� �������� ����� ��������� ����� ����������. �����, ���� �� �������, ���� ���������� � ������ ��������� �� � ��������� grade. �� ������ ����� �������� �������� ������� ������������ �� ���������� �������� � ��������� ������ �� ������ ���������.


��� ������ ������������� ������ � ������� 2 �������.

1 �������: ���������� ������� ���� ��� ������� ��������.

`average_mark(Sub,Mark)` - �������� ������� ���� ��� ��������� ��������.

������� �������������:
```prolog
| ?- average_mark('���������� ����������������',X).
X = 4.1071428571428568
| ?- average_mark('�������������� ������',X).
X = 4.0357142857142856
| ?- average_mark('����������',X).
X = 3.8571428571428572
```

����������:
```prolog
% ����� ������ �� ��������
% (������ ������, ����� ������)
sum_grades([],0).
sum_grades([grade(X,Y)|T],N):- sum_grades(T,M), N is Y + M.

% ������� ���� ��� ��������
% (�������� ��������, ������� ������)
average_mark(Sub,Mark):-
    subject(Sub,Y),
    sum_grades(Y, Sum),
    length(Y, Len),
    Mark is Sum / Len.
```
������� �������� ������ ���� ������ �� ��������, ����� ������������ ����� ���� ������ �� ����� ��������, ����� ������� ������� ���� (����� ����� �� ���������� ������).

2 �������: ��� ������ ������, ����� ���������� ��������� ���������

`do_not_pass_group(Gr,Count)` - ������� ���������� ��������� ��������� � �������� ������

������� �������������:
```prolog
| ?- do_not_pass_group(101,X).
X = 3
| ?- do_not_pass_group(102,X).
X = 3
| ?- do_not_pass_group(103,X).
X = 2
| ?- do_not_pass_group(104,X).
X = 2
```

����������:
```prolog
% ������ ���� ������ �� ���� ���������
% (������ ���������, ������ ������)
all_marks([],L).
all_marks([H|T], List_pass):-subject(H,X), all_marks(T, New_list), append(X, New_list, List_pass).

% �������� ������������� ������, ����� ���� � ������ ���� � ��� �� ������� ������� ������ ����� 2 �� ������ ���������, �� ���������� ���� ���� ���
delete_all(_,[],[]).
delete_all(X,[X|L],L1):-delete_all(X,L,L1).
delete_all(X,[Y|L],[Y|L1]):- X \= Y, delete_all(X,L,L1).

remove_same([],[]).
remove_same([H|T],[H|T1]):-delete_all(H,T,T2), remove_same(T2,T1).

% ���������, ������� ���������, ���������� 2, ������� � ������ ������
% (������ ���� ������, ������ ������, ���������� ��������� ��������� �� ������)
check([],L,0).
check([grade(X,Y)|T],L,N):- Y < 3, my_member(X, L), !, check(T,L,M), N is M + 1.
check([_|T],L,N):-check(T,L,N).


% ���������� ��������� ��������� � ������
% (����� ������, ����� ���������)
do_not_pass_group(Gr,Count):-
    group(Gr, Lgroup),
    findall(Sub, subject(Sub,_), Subs),
    all_marks(Subs, List_pass),
    remove_same(List_dont_pass, New),
    check(New, Lgroup, Count).
```
�������� ������ ��������� ������ ������, �������� ������ ���� ��������� ���������, �������� ��� ������ �� ���� ���������, ������� ������������� ������, ����� ���� ���� � ��� �� ������� �� ���� ������ 1 ��������, �� ������� ��� ������, ��������� ������� �� ��������� ��������� �������� ���������� �������� ������.

3 �������: ����� ���������� ��������� ��������� ��� ������� �� ���������

`do_not_pass_sub(Sub,Count)` - ������� ���������� ��������� ��������� ��� ��������� ��������

������� �������������:
```prolog
| ?- do_not_pass_sub('���������� ����������������',X).
X = 3
| ?- do_not_pass_sub('�������������� ������',X).
X = 1
| ?- do_not_pass_sub('����������',X).
X = 2
```

����������:
```prolog
%(������ ������, ����� ���������)
count_do_not_pass([],0).
count_do_not_pass([grade(X,Y)|T],N):- Y < 3, !, count_do_not_pass(T,M), N is M + 1.
count_do_not_pass([_|T],N):-count_do_not_pass(T,N).

% (�������� ��������, ����� ���������)
do_not_pass_sub(Sub,Count):-
    subject(Sub,Y),
    count_do_not_pass(Y,Count).
```
�������� ������ ������ �� ������� ��������, ������� ������� �� ��� ������.

## ������

� ������������ ������ �� ��������� ��� ���-���� �������, � ������� -- ��� ���������� �������. �� �������� �������, ��� ��� �������� � ������ �������. ��������� �� ������� �������� ��������, �� �� ���� ���������� ������ ���������� ���������. �������������, ��� ����� ���������������� ���������� ����������. ���� � ����� �����������, ��� ����� �������� ������������ ���������� ������ � �������. �� ��� ������ ����� �������, ��� ���������� ���������������� �������� ����� ������������� ������� �����-�� ��������� ������. ��������� ������ � ��������� ��� � ������ �����, ��� ����� �������� ������� ������ �� ��������� �������. � ��������� ��� �������� ���� ���������, ��� ������ ������� �����������. ����� ���������� ��������� ���������� ���������, �������� �����, � ����� ������� � ��� ����������� �������, ��� ���� ��� �� ������ ���� ��������. �����, ����� ������ ��������� ����������� ���������������� ����� ������ ��������. ����� ������������� � �����-�� ������������� ����� ��� ���� ��������, ������ ����� ��������� ��� ��������������� ������. ��� �������, ����� ������� ������ �� ����������� ������, ��� ��� ��������, � ����� ��������� ���� ���� � ����� ��������� ��������. ������, ��� � ���� ������ � ��� ���� ����������� �� ������� ������� � ������ ����������� ������ � ���������� ���������������� � � ������� � ���������.
