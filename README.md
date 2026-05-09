
<p align="center">
  <img src="https://www.must.edu.mn/media/uploads/2022/08/10/image-20220810124218-2.png" alt="SICT Logo" width="150"/>
</p>

<h1 align="center">ШИНЖЛЭХ УХААН, ТЕХНОЛОГИЙН ИХ СУРГУУЛЬ</h1>
<h2 align="center">МЭДЭЭЛЭЛ, ХОЛБООНЫ ТЕХНОЛОГИЙН СУРГУУЛЬ</h2>

---

## ЛАБОРАТОРИЙН АЖЛЫН ТАЙЛАН  10.2

---

**Хичээл:** F.CSM202 Объект хандалтат программчлал  
**Хичээлийн жил:** 2025-2026 оны хавар  

**Хичээл заасан багш:** Х.Хулан /F.CS17/  
**Лабораторийн ажил гүйцэтгэсэн:** Оюутан -Г.Ууганбаяр /B242290002/  

<p align="center">
 Улаанбаатар хот  
</p>

---
## Тойм
Энэ лабораторид Java дахь нэгжийн тестлэлийг JUnit болон JaCoCo ашиглан судалсан.

## Хийсэн зүйлс

### 1. LinkedIntQueue — Тодорхойлолтын тестлэл
`IntQueue` интерфэйсийн тодорхойлолтод үндэслэн дараах тестүүдийг бичсэн:

- `testIsEmpty` — хоосон queue шалгах
- `testNotEmpty` — элемент нэмсний дараа хоосон биш эсэхийг шалгах
- `testPeekEmptyQueue` — хоосон үед `peek()` null буцаадаг эсэхийг шалгах
- `testPeekNoEmptyQueue` — элемент байхад `peek()` зөв утга буцаадаг эсэхийг шалгах
- `testEnqueue` — элемент нэмэх
- `testDequeue` — элемент гаргах дарааллыг шалгах
- `testContent` — файлаас уншиж тестлэх

### 2. ArrayIntQueue — Бүтцийн тестлэл
`ArrayIntQueue` классын дотоод хэрэгжилтийг тестлэж **3 алдаа** олж засварласан:

| Метод | Алдаа | Засвар |
|-------|-------|--------|
| `isEmpty()` | `size >= 0` үргэлж true буцаана | `size == 0` болгосон |
| `peek()` | хоосон үед null буцаадаггүй | `if (isEmpty()) return null` нэмсэн |
| `ensureCapacity()` | array өргөтгөлд индекс буруу | `newData[oldCapacity - head + i]` болгосон |

### 3. JaCoCo хамралт
Нэмэлт тестүүд бичиж **100% мөрийн хамралтад** хүрсэн:

- `testClear` — `clear()` методыг тестлэх
- `testDequeueEmpty` — хоосон queue-д `dequeue()` тестлэх
- `testEnsureCapacity` — array өргөтгөлийг тестлэх
- `testEnsureCapacityWithHead` — `head` дунд байх үед өргөтгөлийг тестлэх

## Тест ажиллуулах

```bash
cd Java
mvn test
```

## Хамралтын тайлан харах
```bash
mvn test
mvn jacoco:report
start target/site/jacoco/index.html
```
## Технологи
- Java 21
- JUnit 4
- JaCoCo 0.8.11
- Maven
