# БОББИ ИЩЕТ СОЛНЦЕ — версия для интернета

Статичный сайт. Один файл `index.html`, ничего собирать не надо.
Работает и без Firebase — тогда прогресс просто хранится в браузере.

## Шаг 1. Firebase — вход через Google (10 минут)

1. https://console.firebase.google.com → **Add project** → имя `bobby` → создать
2. Слева **Build → Authentication → Get started**
3. Вкладка **Sign-in method** → **Google** → включить → **Save**
4. Слева **Build → Firestore Database → Create database** → **Production mode** → регион `eur3`
5. Вкладка **Rules** → стереть всё → вставить содержимое `firestore.rules` → **Publish**
6. Шестерёнка сверху → **Project settings** → блок **Your apps** → иконка **</>** (Web)
   → имя `bobby` → **Register app** → скопировать объект `firebaseConfig`
7. Открыть `index.html`, найти `ВСТАВЬ СЮДА КОНФИГ ИЗ FIREBASE`, вставить свои
   `apiKey`, `authDomain`, `projectId`, `appId`

## Шаг 2. Vercel — домен

1. https://vercel.com → **Continue with GitHub**
2. **Add New → Project** → выбрать этот репозиторий → **Deploy**
3. Через минуту будет адрес вида `bobby-xxxx.vercel.app`

## Шаг 3. Разрешить домен в Firebase (ОБЯЗАТЕЛЬНО)

Firebase → **Authentication → Settings → Authorized domains → Add domain**
→ вписать домен с Vercel (без `https://`).

Без этого шага кнопка входа будет ругаться `auth/unauthorized-domain`.

## Свой домен вместо vercel.app

Домен надо купить (например на Namecheap, ~$10/год), потом
Vercel → Settings → Domains → Add. Vercel покажет, какие DNS-записи прописать.
После этого добавь новый домен и в Authorized domains из шага 3.

## Проверка

Открой сайт на ноуте, войди через Google, пройди пару уровней.
Открой на телефоне, войди тем же гуглом — уровни должны быть уже пройдены.
В меню под кнопками должно быть написано «☁ прогресс в аккаунте Google».
