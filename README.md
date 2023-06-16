<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

מומלץ להתקין תחילה nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) , ולאחר מכן `direnv allow` לאחר הכניסה לספרייה ( [ה-.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) יתבצע אוטומטית לאחר הכניסה לספרייה).

המשמעות היא: תרגום סינית ליפנית, קוריאנית, אנגלית, תרגום לאנגלית לכל שאר השפות. אם אתה רוצה לתמוך רק בסינית ובאנגלית, אתה יכול פשוט לכתוב `zh: en` .

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

### הוראות אוטומציה לתרגום מסמכים

ראה מאגר קודים [xxai-art/doc](https://github.com/xxai-art/doc)

מומלץ להתקין תחילה nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) , ולאחר מכן `direnv allow` לאחר הכניסה לספרייה ( [ה-.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) יתבצע אוטומטית לאחר הכניסה לספרייה).

על מנת להימנע מבסיס הקוד הגדול שתורגם למאות שפות, יצרתי בסיס קוד נפרד לכל שפה ויצרתי ארגון לאחסון בסיס הקוד

הגדרת משתנה הסביבה `GITHUB_ACCESS_TOKEN` ולאחר מכן הפעלת [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) תיצור אוטומטית את מאגר הקוד.

כמובן, אתה יכול גם לשים את זה בבסיס קוד.

הפניה לסקריפט תרגום [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

קוד הסקריפט מתפרש כך:

[bunx](https://bun.sh/docs/cli/bunx) הוא תחליף ל-npx, שהוא מהיר יותר. כמובן, אם אין לך bun מותקן, אתה יכול להשתמש `npx` במקום.

`bunx mdt zh` מעבד את `.mdt` בספריית zh כ- `.md` , ראה את 2 הקבצים המקושרים למטה

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` הוא קוד הליבה לתרגום (אם יש לך רק `nodejs` מותקנים, אבל `bun` ו- `direnv` לא מותקנים, אתה יכול גם להפעיל את `npx i18n` כדי לתרגם).

זה ינתח [את i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , התצורה של `i18n.yml` במסמך זה היא כדלקמן:

```
en:
zh: ja ko en
```

המשמעות היא: תרגום סינית ליפנית, קוריאנית, אנגלית, תרגום לאנגלית לכל שאר השפות. אם אתה רוצה לתמוך רק בסינית ובאנגלית, אתה יכול פשוט לכתוב `zh: en` .

האחרון הוא [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , אשר מחלץ את התוכן בין הכותרת הראשית לכותרת המשנה הראשונה של `README.md` של כל שפה כדי ליצור ערך `README.md` . הקוד מאוד פשוט, אתה יכול להסתכל עליו בעצמך.

Google API משמש לתרגום חופשי. אם אינך יכול לגשת ל-Google, אנא הגדר והגדר פרוקסי, כגון:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

סקריפט התרגום יפיק מטמון מתורגם בספריית `.i18n` , אנא בדוק אותו עם `git status` והוסף אותו למאגר הקוד כדי למנוע תרגומים חוזרים.

אנא הפעל את `bunx i18n` בכל פעם שאתה משנה את התרגום כדי לעדכן את המטמון.

אם הטקסט המקורי והתרגום משתנים בו-זמנית, המטמון יתבלבל, כך שאם תרצה לשנות, תוכל לשנות רק אחד, ולאחר מכן להפעיל `bunx i18n` כדי לעדכן את המטמון.
