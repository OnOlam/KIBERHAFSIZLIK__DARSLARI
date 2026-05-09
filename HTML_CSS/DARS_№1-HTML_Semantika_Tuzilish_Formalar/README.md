# 🎓DARS №1 ──  HTML: Semantika, Tuzilish, Formalar

---

## 📖 NAZARIY QISM

### HTML nima va u nima uchun?
HTML ── bu brauzerga sahifaning **tuzilishini** aytadigon til. CSS ko'rinishini, JS esa xatti-harakatini boshqaradi. HTML bularning poydevori.

### Semantik HTML ── nima farqi bor?
Quyida ikkita kod bir xil ko'rinadi brauzerda lekin ular bir xil emas:
```html
<!-- ❌ Semantik emas -->
<div class="header">Sarlavha</div>
<div class="nav">Menyu</div>
<div class="article">Maqola matni</div>

<!-- ✅ Semantik -->
<header>Sarlavha</header>
<nav>Menyu</nav>
<article>Maqola matni</article>
```

### Nima uchun muhim?
── SEO, accessiblity va eng muhimi: kiberhafsizlikda DOM tahlili qilganda semantik tuzilgan sahifani tushunish ancha oson.

---

### Asosiy semantik teglar:
| Teg | Maqsad |
|-----|--------|
| <header> | Sarlavha, logo, navigatsiya |
| <nav> | Navigatsiya havolalari |
| <main> | Sahifaning asosiy kontenti |
| <section> | Mavzuviy bo'lim |
| <article> | Mustaqil kontent (blog post va h.k.) |
| <aside> | Yon panel, qo'shimcha ma'lumot |
| <footer> | Pastki qism |
| <figure> + <figcaption> | Rasm + izoh |

---

### Forma va Input turlari ── kiberhafsizlik uchun juda muhim!
Formalar ── bu web hujumlarning asosiy kirish nuqtasi (XSS, SQLi). Shuning uchun ularni yaxshi bilishing shart:

```html
<form action="/login" method="POST">
    <!-- Text turlari -->
    <input type="text" name="username" placeholder="Login">
    <input type="password" name="password">
    <input type="email" name="email">
    <input type="number" name="yosh" min="1" max="100">

    <!-- Maxsus inputlar -->
    <input type="hidden" name="csrf_token" value="abc123">
    <input type="file" name="avatar" accept="image/*">
    <input type="search" name="q">

    <!-- Boshqaruv elementlari -->
    <select name="rol">
        <option value="user">Foydalanuvchi</option>
        <option value="admin">Admin</option>
    </select>

    <textarea name="izoh" row="4"></textarea>

    <button type="submit">Kirish</button>
```

### Kiberhafsizlik nuqtai nazari:
type="hidden" maydonlari brauzerda ko'rinmaydi, lekin DevTools orqali ko'rsa bo'ladi va o'zgartirsa bo'ladi ── bu zaiflik!

---

## 🛠️ AMALIY QISM

### Vazifa #1 ── Dars ichi
Quyidagi talablar asosida HTML sahifa yaratasan.

#### Shartlar:
1. Sahifa <!DOCTYPE html> bilan boshlansin
2. **Faqat semantik reglar** ishlatilsin (div ishlatilma asosiy tuzilish uchun)
3. Sahifada bo'lishi kerak:
    - <header> ── sayt nomi va <nav> (3ta havola: Bosh sahifa, Haqimizda, Bog'lanish)
    - <main> ichida <section> ── "Ro'yhatdan o'tish" sarlavhasi bilan
    - Forma: name, email, password, confirm_password, tel (telefon), data (tug'ilgan kun), select (rol: foydalanuvchi/moderator), checkbox (shartlarni qabul qilaman), submit tugmasi
    - <footer> ── muallif huquqi matni
4. Har bir input da name atributi bo'lsin (xavfsizlik nuqtai nazaridan muhim)
5. Formada method="POST" bo'lsin

**Ko'rsatma:** Faqat HTML yoz, CSS kerak emas. Brauzerda ochib ko'r, tuzilish to'g'ri bo'lsin.

---

## 📝 UY VAZIFASI

Bajargan HTML faylingni GitHub'ga joyla
**Qo'shimcha vazifa (ixtiyoriy, lekin tavsiya etiladi):**
DevTools'ni (F12) ochib, o'z foemangizdagi hidden input qo'sh va u qiymatbu DevTools orqali o'zgartura ilushingni ko'r. Bu kiberhafsizlik uchun muhim tushuncha.

---

## ⚠️ QOIDA VA ESLATMA

Darslardagi barcha bilimlarlar faqat **o'rganish** maqsadida, bu bilimlarni boshqa birovlarga tajovuzkorlik maqsadlarda ishlatmang, **hamma javobgarlik o'zingizni bo'yningizda‼️**