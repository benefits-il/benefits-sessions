---
type: cheat-sheet
unit: git-github-terminal
session: 4
title: כרטיסיית פקודות Git + Terminal
---

# כרטיסיית פקודות Git + Terminal
שימרו את זה לידכם בזמן העבודה. כל פקודה היא אמיתית — העתיקו אותה, הרצו אותה. ההערות אחרי כל פקודה נשמרו בעברית בכוונה (תוכן ייחוס מילולי — הפקודות עצמן הן אוניברסליות ולעולם אינן מתורגמות).

## Terminal — ניווט

```
pwd            # איפה אני? מדפיס את הנתיב הנוכחי
ls             # מה יש כאן? מציג קבצים ותיקיות
cd <folder>    # להיכנס לתיקייה
cd ..          # לעלות תיקייה אחת
mkdir <name>   # ליצור תיקייה חדשה
```

## Git מקומי — מכונת הזמן

```
git --version                          # לבדוק ש-Git מותקן
git config --global user.name "..."    # הגדרת זהות (פעם אחת)
git config --global user.email "..."   # הגדרת מייל (פעם אחת)
git init                               # להפוך תיקייה ל-repo
git status                             # מה השתנה? (הרדאר)
git add .                              # להעביר הכל ל-staging
git commit -m "message"                # לצלם snapshot
git log                                # לראות היסטוריית commits (q ליציאה)
```

## Git בענן — GitHub

```
git remote add origin <URL>   # לחבר את התיקייה למאגר בענן (פעם אחת)
git branch -M main            # לוודא שהענף הראשי נקרא main
git push -u origin main       # דחיפה ראשונה לענן
git push                      # כל דחיפה הבאה (אחרי ההגדרה הראשונה)
git clone <URL>               # להוריד repo של מישהו אחר
```

## פתרון בעיות (Troubleshooting)

| הבעיה | הסיבה | הפתרון |
|---|---|---|
| `Please tell me who you are` | לא הוגדרה זהות לפני ה-commit | הרצו את שתי פקודות ה-`git config` ונסו שוב |
| Push rejected (`non-fast-forward`) | קובץ README נוצר בענן והתנגש עם המקומי | `git pull --rebase origin main` ואז push, או ליצור repo ריק ללא README |
| `remote origin already exists` | פקודת `git remote add origin` הורצה פעמיים | `git remote set-url origin <URL>` |
| אין חלון אימות בדפדפן, מבקש סיסמה | גרסת Git ישנה ללא Credential Manager | עדכנו את Git מ-git-scm.com ונסו שוב |
| `nothing to commit` אחרי עריכה | הקובץ לא נשמר בעורך לפני `git add` | שמרו את הקובץ, ואז `git add .` |
| המסך תקוע על `(END)` | `git log` / `git status` נמצא במצב תצוגה | לחצו על `q` |
| פקודות מתנהגות מוזר ב-Windows | נפתח CMD במקום PowerShell | פתחו את PowerShell |
| הפקודה "נשברת" לאחר הדבקה | מרכאות חכמות (Smart quotes) כתוצאה מהעתקה ממסמך | הקלידו מרכאות רגילות |
