````markdown
---

## テーブル：`logs`

| id  | level   | message                            | created_at          |
|------|---------|----------------------------------|---------------------|
| 101  | INFO    | user login success               | 2025-07-01 09:00:00 |
| 102  | ERROR   | Password change failed           | 2025-07-01 09:05:00 |
| 103  | INFO    | username change                  | 2025-07-01 09:10:00 |
| 104  | WARN    | Network configuration changed    | 2025-07-01 09:20:00 |
| 105  | INFO    | System reboot initiated          | 2025-07-01 09:30:00 |

---

## ストーリー

あなたはシステム運用担当者。  
重要なログの中からパスワードのヒントになるキーワードを取り出すよう指示された。  
取り出せるキーワードは何か？

---

## 実行したSQL

```sql
SELECT RIGHT(message, 6) AS keyword
FROM logs
WHERE level = 'INFO' AND message LIKE '%user%'
ORDER BY created_at DESC
LIMIT 1;
````

---

## 【RIGHT() 関数リファレンス】

### 概要

`RIGHT(string, n)` 関数は、指定した文字列 `string` の右端から `n` 文字分を抽出して返します。

### 構文

```
RIGHT(string, n)
```

---

```
```


