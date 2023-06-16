<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

חלק מקוד האתר הוא קוד פתוח, מוזמן לעזור באופטימיזציה של התרגום.

## קוד קצה

* [קוד קצה](https://github.com/xxai-art/web)
* [חבילות שפה עבור האתר כולו](https://github.com/xxai-art/web/tree/main/i18n)
* [חבילות שפה עבור מודולי כניסה](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [תיעוד רב לשוני באתר](https://github.com/xxai-doc)

שפת התכנות הקדמית היא [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , אשר מוסיפה כמה תכונות המבוססות על תחביר coffeescript, ראה [./coffee_plus.md](./coffee_plus.md) .

## בינלאומי של אתרי אינטרנט ומסמכים

התבסס על 3 הפרויקטים הבאים

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  הסיומת היא `.mdt` , אתה יכול להשתמש בתחביר הדומה ל- `<+ ./coffee_plus/import.js>` כדי להתייחס לקבצים חיצוניים, וליצור סימון עם הסיומת `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  תרגום Markdown לא יתרגם קודים וקישורים, וישמור משפטים מתורגמים במטמון. אם התרגום שונה אך הטקסט המקורי לא שונה, ביצועו שוב לא יחליף את השינוי של התרגום.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  קבצי שפה לתרגום אתרים שנוצרו על ידי `yaml` .
