### Client-side-again
## Objetivo
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/6353/` ([link](https://jupiter.challenges.picoctf.org/problem/6353/)) or http://jupiter.challenges.picoctf.org:6353
## Hints
1. What is obfuscation?
## Datos de acceso al nivel
## Solución
1. Inspeccionar el código fuente.
2. Buscamos una opción para hacerlo legible.
```bash
'use strict';
/** @type {!Array} */
var _0x5a46 = ["c2047}", "_again_6", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
(function(data, i) {
  /**
   * @param {number} isLE
   * @return {undefined}
   */
  var write = function(isLE) {
    for (; --isLE;) {
      data["push"](data["shift"]());
    }
  };
  write(++i);
})(_0x5a46, 435);
/**
 * @param {string} level
 * @param {?} ai_test
 * @return {?}
 */
var _0x4b5b = function(level, ai_test) {
  /** @type {number} */
  level = level - 0;
  var rowsOfColumns = _0x5a46[level];
  return rowsOfColumns;
};
/**
 * @return {undefined}
 */
function verify() {
  checkpass = document[_0x4b5b("0x0")]("pass")[_0x4b5b("0x1")];
  /** @type {number} */
  split = 4;
  if (checkpass[_0x4b5b("0x2")](0, split * 2) == _0x4b5b("0x3")) {
    if (checkpass[_0x4b5b("0x2")](7, 9) == "{n") {
      if (checkpass[_0x4b5b("0x2")](split * 2, split * 2 * 2) == _0x4b5b("0x4")) {
        if (checkpass[_0x4b5b("0x2")](3, 6) == "oCT") {
          if (checkpass[_0x4b5b("0x2")](split * 3 * 2, split * 4 * 2) == _0x4b5b("0x5")) {
            if (checkpass["substring"](6, 11) == "F{not") {
                if (checkpass[_0x4b5b("0x2")](12, 16) == _0x4b5b("0x7")) {
              if (checkpass[_0x4b5b("0x2")](split * 2 * 2, split * 3 * 2) == _0x4b5b("0x6")) {
                  alert(_0x4b5b("0x8"));
                }
              }
            }
          }
        }
      }
    }
  } else {
    alert(_0x4b5b("0x9"));
  }
}
;
```

3. Utilizamos la consola Javascript del navegador ("Developer Tools") para evaluar y leer sus valores: 0x4b5b 
    0x4b5b

```bash
>>> _0x4b5b
function _0x4b5b()

>>> _0x4b5b("0x0")
"getElementById"
>>> _0x4b5b("0x1")
"value"
>>> _0x4b5b("0x2")
"substring"
>>> _0x4b5b("0x3")
"picoCTF{"
>>> _0x4b5b("0x4")
"not_this"
>>> _0x4b5b("0x5")
"55670}"
>>> _0x4b5b("0x6")
"_again_0"
>>> _0x4b5b("0x7")
"this"
>>> _0x4b5b("0x8")
"Password Verified"
>>> _0x4b5b("0x9")
"Incorrect password"
```

4. Sustituimos.

```bash
function verify() {
  checkpass = document["getElementById"]("pass")["value"];
  /** @type {number} */
  split = 4;
  if (checkpass["substring"](0, split * 2) == "picoCTF{") {
    if (checkpass["substring"](7, 9) == "{n") {
      if (checkpass["substring"](split * 2, split * 2 * 2) == "not_this") {
        if (checkpass["substring"](3, 6) == "oCT") {
          if (checkpass["substring"](split * 3 * 2, split * 4 * 2) == "55670}") {
            if (checkpass["substring"](6, 11) == "F{not") {
                if (checkpass["substring"](12, 16) == "this") {
              if (checkpass["substring"](split * 2 * 2, split * 3 * 2) == "_again_0") {
                  alert("Password Verified");
                }
              }
            }
          }
        }
      }
    }
  } else {
    alert("Incorrect password");
  }
}
```


Tenemos:

```bash
(0-8)      == "picoCTF{"
(7-9)      == "{n"
(8-16)     == "not_this"
(3-6)      == "oCT"
(24-32)    == "c2047}"
(6-11)     == "F{not"
(16-24)    == "_again_6"
(12-16)    == "this"
```

5. Transformamos las subcadenas de javascript en código de Python y ejecutámos.

```bash
text = """
  if (checkpass["substring"](0, split * 2) == "picoCTF{") {
    if (checkpass["substring"](7, 9) == "{n") {
      if (checkpass["substring"](split * 2, split * 2 * 2) == "not_this") {
        if (checkpass["substring"](3, 6) == "oCT") {
          if (checkpass["substring"](split * 3 * 2, split * 4 * 2) == "55670}") {
            if (checkpass["substring"](6, 11) == "F{not") {
                if (checkpass["substring"](12, 16) == "this") {
              if (checkpass["substring"](split * 2 * 2, split * 3 * 2) == "_again_0") {
"""

flag = [None] * 32
split = 4
for line in text.split("\n"):
    line = line.strip()
    if line == "": 
        continue
    line = line.replace('if (checkpass["substring"](', 'flag[').replace(', ', ":").replace(') == ', '] = ').replace(') {', '')
    exec(line)

print "".join(flag)
```


```bash
root@kali:/media/sf_CTFs/pico/Client-side-again# python solve.py
flag[0:split * 2] = "picoCTF{"
flag[7:9] = "{n"
flag[split * 2:split * 2 * 2] = "not_this"
flag[3:6] = "oCT"
flag[split * 3 * 2:split * 4 * 2] = "55670}"
flag[6:11] = "F{not"
flag[12:16] = "this"
flag[split * 2 * 2:split * 3 * 2] = "_again_0"
picoCTF{not_this_again_055670}
```
## Notas adicionales
## Referencias
