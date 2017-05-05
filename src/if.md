# if

条件分岐をしたい時には `if` を使用します。

```cpp
int x = 5;

if (x == 5) {
    ...
}
```

`if` の条件を満たさなかった場合に何か処理をしたければ `else` を使用します。

```cpp
int x = 5;

if (x == 5) {
    ...
} else {
    ...
}
```

さらに別の条件で処理を分岐したければ `else if` を使用します。

```cpp
int x = 5;

if (x == 5) {
    ...
} else if (x == 6) {
    ...
} else {
    ...
}
```