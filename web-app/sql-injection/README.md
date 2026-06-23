# SQL Injection

SQL Injection は、ユーザー入力が適切に検証されず SQL クエリに組み込まれることで発生する脆弱性。

---

## Category

Web Application Security

---

## Overview

攻撃者は入力フォームやURLパラメータへSQL文を注入し、データベース操作を行うことができる。

影響例

・認証回避
・情報漏洩
・データ改ざん
・データ削除

---

## Example

入力

```sql
' OR '1'='1
```

脆弱なクエリ

```sql
SELECT * FROM users
WHERE username = '$user'
AND password = '$pass';
```

---

## Detection

・エラーメッセージの確認
・Burp Suite によるパラメータ改変
・SQLMap による検証

---

## Mitigation

・Prepared Statement
・Parameterized Query
・入力値検証
・最小権限の原則

---

## Lab

・DVWA
・OWASP Juice Shop

