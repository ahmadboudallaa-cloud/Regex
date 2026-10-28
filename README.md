# 📘 README — Les Regex les plus utilisées

## 1. Les caractères de base

| Caractère | Signification | Exemple |
|---|---|---|
| `^` | Début du texte | `/^Ahmed/` |
| `$` | Fin du texte | `/123$/` |
| `.` | N'importe quel caractère (sauf certains retours à la ligne) | `/a.b/` |
| `\d` | Un chiffre de 0 à 9 | `/\d/` |
| `\D` | Un caractère qui n'est pas un chiffre | `/\D/` |
| `\w` | Lettre ASCII, chiffre ou `_` | `/\w/` |
| `\s` | Un espace blanc | `/\s/` |

## 2. Les crochets `[ ]`

| Regex | Signification |
|---|---|
| `[a-z]` | Lettres minuscules anglaises |
| `[A-Z]` | Lettres majuscules anglaises |
| `[a-zA-Z]` | Lettres minuscules et majuscules |
| `[0-9]` | Chiffres de 0 à 9 |
| `[a-zA-Z0-9]` | Lettres ou chiffres |
| `[^0-9]` | Tout caractère sauf un chiffre |

## 3. Les quantificateurs

| Caractère | Signification | Exemple |
|---|---|---|
| `+` | Une ou plusieurs fois | `/\d+/` |
| `*` | Zéro ou plusieurs fois | `/\d*/` |
| `?` | Zéro ou une fois | `/colou?r/` |
| `{n}` | Exactement n fois | `/\d{8}/` |
| `{n,m}` | Entre n et m fois | `/\d{2,5}/` |

## 4. Les groupes et les conditions

| Syntaxe | Signification |
|---|---|
| `(abc)` | Regroupe des caractères |
| `a|b` | `a` OU `b` |
| `(?=...)` | Vérifie qu'une condition est vraie |
| `(?!...)` | Vérifie qu'une condition est fausse |

## 5. Exemples courants

### Exactement 8 chiffres

```javascript
/^\d{8}$/
```

### Lettres uniquement

```javascript
/^[a-zA-Z]+$/
```

### Lettres suivies de chiffres

```javascript
/^[a-zA-Z]+\d+$/
```

### Au moins une lettre et un chiffre

```javascript
/^(?=.*[a-zA-Z])(?=.*\d).+$/
```

### Mot de passe d'au moins 8 caractères

```javascript
/^.{8,}$/
```

## 6. Tester une Regex

```javascript
const regex = /^\d{8}$/;

console.log(regex.test("12345678")); // true
console.log(regex.test("123abc78")); // false
```

- `true` : le texte respecte la règle.
- `false` : le texte ne respecte pas la règle.

**À apprendre en premier :** `^`, `$`, `\d`, `[a-zA-Z]`, `+`, `*`, `?`, `{n}` et `.test()`