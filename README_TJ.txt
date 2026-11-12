MIR CAPITAL — дастури насб ва ба кор даровардан

1) ФАЙЛҲОРО БА VERCEL БОР КУНЕД
- ZIP-ро кушоед.
- Маҳз файлҳои index.html, styles.css, app.js, config.js ва папкаи sql бояд дар решаи лоиҳа бошанд.
- Дар Vercel лоиҳаи Static / Other интихоб шавад; Framework Preset = Other.
- Root Directory бояд папкае бошад, ки index.html дар дохилаш аст.
- Build Command холӣ, Output Directory = . (ё холӣ).
- Deploy кунед. ZIP-ро танҳо кушодан сайтро нав намекунад — deploy ҳатмист.

2) SUPABASE — БАЗАИ МАЪЛУМОТ
- Ба https://supabase.com/dashboard/project/kakdgflxnqfoxhxiuasa/sql/new дароед.
- Файли sql/schema.sql-ро кушоед, тамоми матнашро нусха карда дар SQL Editor гузоред.
- Run пахш кунед. Агар хатои SQL барояд, матни хатогиро нигоҳ доред.

3) SUPABASE — EMAIL AUTH
- Authentication → URL Configuration.
- Site URL = домени воқеии Vercel-и шумо (масалан https://your-project.vercel.app).
- Ҳамон доменро ба Redirect URLs илова кунед: https://your-project.vercel.app/**
- Authentication → Sign In / Providers → Email фаъол бошад.
- Агар Confirm email фаъол бошад, баъди сабти ном бояд email-ро тасдиқ кунед. Барои санҷиши аввал метавонед онро муваққатан хомӯш кунед; пеш аз кушодани сайт барои мардум SMTP-и дуруст насб карда, тасдиқи email-ро фаъол кунед.

4) АДМИНИСТРАТОР
- Аввал бо email-и худ аз сайт аккаунт созед ва тасдиқ кунед.
- Дар Supabase → SQL Editor ин фармонро иҷро кунед, email-и худро ҷойгузин кунед:
  update public.profiles set role='admin', plan='vip' where id=(select id from auth.users where email='EMAIL-и-ХУД');
- Баъд аз сайт баромада, аз нав ворид шавед. Панели ADMIN ONLY бояд намоён шавад.

5) РЕГИСТРАЦИЯ ВА ТЕЛЕФОН
- Рақами телефон бо коди кишвар интихоб мешавад; Тоҷикистон +992 пешфарз аст.
- Номи пурра, email, рақами телефон ва пароли ҳадди ақал 8-рақама лозим аст.
- Барои воридшавӣ email ва пароль истифода мешаванд.
- Агар тасдиқи email фаъол бошад, аввал паёми тасдиқро дар почта кушоед.

6) БЕХАТАРӢ
- Калиди sb_publishable_ дар config.js барои браузер аст ва метавонад ошкор бошад.
- ҲЕҶ ГОҲ service_role / secret key, DB password ё пароли Supabase-ро ба config.js нагузоред.
- RLS дар SQL фаъол аст. Корбар наметавонад аз браузер нақши admin ё сатҳи VIP-и худро иваз кунад.
- Барои видеоҳои PREMIUM/VIP аз хостинги видеоии дорои signed URLs истифода баред. Линки оддии кушода ҳифзи пурраи видео нест.

7) САНҶИШ ДАР ТЕЛЕФОН
- Сайти deploy-шударо дар Chrome кушоед.
- Агар версияи кӯҳна бошад: Chrome → ⋮ → Settings → Site settings → Storage → домени сайт → Clear & reset; баъд сайтро аз нав кушоед.
- Санҷед: забонҳо RU/UZ/EN, кушодани формаи регистрация, интихоби +992, фиристодани форма, тасдиқи email ва воридшавӣ.

ЭЗОҲИ МУҲИМ: Манбаъ-код ва responsive layout омода карда шудааст, аммо сабти ном танҳо баъди иҷрои SQL ва танзими URL/email дар Supabase фаъол мешавад. Ман ба аккаунти Supabase ё Vercel-и шумо дастрасӣ надорам ва наметавонам аз ин ҷо deploy-и зиндаро иҷро ё бақайдгирии воқеиро дар ҳисоби шумо тасдиқ кунам.
