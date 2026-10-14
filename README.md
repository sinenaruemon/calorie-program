# Calorie Program

**English** | [ภาษาไทย](#ภาษาไทย)

A simple, single-file web app that estimates how many calories you should eat per day based on your body weight, then lets you log what you eat and see how much is left.

No installation, no dependencies, no server. Just open `index.html` in a browser.

## Features

- **Daily calorie target** calculated from your weight (height and age are optional for better accuracy)
- **Goal setting**: lose, maintain, or gain weight
- **Daily food log** with a progress bar showing calories eaten, remaining, or over target
- **Thai food quick-pick**: 25 common Thai foods and drinks with searchable, tap-to-add calorie values
- **7-day history chart**: bars turn red on days you went over your target
- **Saved in your browser**: your log is stored locally (localStorage) and never sent anywhere

## How it works

1. Enter your weight (required). Optionally enter height, age, and sex.
2. Choose your activity level and goal.
3. Press **Calculate**. The app shows your daily calorie target.
4. Add the foods you eat during the day and watch the progress bar.

### Calculation

| Input provided | Basal metabolic rate (BMR) |
| --- | --- |
| Weight only | Male: weight (kg) × 24, Female: weight (kg) × 22 |
| Weight + height + age | [Mifflin-St Jeor](https://en.wikipedia.org/wiki/Basal_metabolic_rate#BMR_estimation_formulas) equation: `10 × kg + 6.25 × cm − 5 × age + 5` (male) or `− 161` (female) |

Then:

```
daily need = BMR × activity factor
target     = daily need + goal adjustment
```

| Activity level | Factor |
| --- | --- |
| Sedentary | 1.2 |
| Light (1–3 days/week) | 1.375 |
| Moderate (3–5 days/week) | 1.55 |
| Heavy (6–7 days/week) | 1.725 |
| Very heavy / physical job | 1.9 |

| Goal | Adjustment |
| --- | --- |
| Lose weight (about 0.5 kg/week) | −500 kcal |
| Maintain | 0 |
| Gain weight | +400 kcal |

The target never goes below a safe minimum (1,500 kcal for men, 1,200 kcal for women).

## Run locally

```bash
git clone https://github.com/sinenaruemon/calorie-program.git
cd calorie-program
```

Then open `index.html` in your browser (double-click the file).

## Publish with GitHub Pages

1. Push `index.html` to the `main` branch.
2. In your repository, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute, the app is live at `https://sinenaruemon.github.io/calorie-program/`.

## Notes

- Calorie values for foods are rough estimates per serving. Real values vary by restaurant and portion size.
- Results are estimates and **not medical advice**. If you have a medical condition or are pregnant, consult a doctor or dietitian.
- Because data is stored in the browser, it stays on that device and browser only. Clearing site data removes your history.

---

# ภาษาไทย

[English](#calorie-program) | **ภาษาไทย**

เว็บแอพไฟล์เดียวสำหรับประมาณแคลอรี่ที่ควรกินต่อวันจากน้ำหนักตัว แล้วจดอาหารที่กินในแต่ละวันเพื่อดูว่าเหลืออีกเท่าไร

ไม่ต้องติดตั้ง ไม่ต้องมีเซิร์ฟเวอร์ แค่เปิดไฟล์ `index.html` ในเบราว์เซอร์

## ฟีเจอร์

- **คำนวณแคลอรี่ต่อวัน** จากน้ำหนัก (ใส่ส่วนสูงและอายุเพิ่มได้เพื่อให้แม่นขึ้น)
- **เลือกเป้าหมาย**: ลด รักษา หรือเพิ่มน้ำหนัก
- **บันทึกอาหารประจำวัน** พร้อมแถบแสดงแคลอรี่ที่กินแล้ว เหลือ หรือเกินเป้าหมาย
- **เลือกอาหารไทยแล้วแตะเพื่อเพิ่ม**: มีอาหารและเครื่องดื่มยอดนิยม 25 รายการ พร้อมช่องค้นหา
- **กราฟ 7 วันล่าสุด**: แท่งสีแดงคือวันที่กินเกินเป้าหมาย
- **เก็บข้อมูลในเบราว์เซอร์**: บันทึกไว้ในเครื่อง (localStorage) ไม่ส่งไปที่อื่น

## วิธีใช้

1. กรอกน้ำหนัก (จำเป็น) และถ้าต้องการจะกรอกส่วนสูง อายุ และเพศด้วยก็ได้
2. เลือกระดับการออกกำลังกายและเป้าหมาย
3. กด **คำนวณแคลอรี่** แอพจะแสดงแคลอรี่ที่ควรกินต่อวัน
4. เพิ่มอาหารที่กินในแต่ละมื้อ แล้วดูแถบความคืบหน้า

### วิธีคำนวณ

| ข้อมูลที่กรอก | อัตราการเผาผลาญพื้นฐาน (BMR) |
| --- | --- |
| น้ำหนักอย่างเดียว | ชาย: น้ำหนัก (กก.) × 24, หญิง: น้ำหนัก (กก.) × 22 |
| น้ำหนัก + ส่วนสูง + อายุ | สูตร Mifflin-St Jeor: `10 × กก. + 6.25 × ซม. − 5 × อายุ + 5` (ชาย) หรือ `− 161` (หญิง) |

จากนั้น:

```
พลังงานที่ใช้ต่อวัน = BMR × ตัวคูณการออกกำลังกาย
เป้าหมาย            = พลังงานที่ใช้ต่อวัน + ค่าปรับตามเป้าหมาย
```

| ระดับการออกกำลังกาย | ตัวคูณ |
| --- | --- |
| แทบไม่ออกกำลังกาย | 1.2 |
| เบา 1-3 วัน/สัปดาห์ | 1.375 |
| ปานกลาง 3-5 วัน/สัปดาห์ | 1.55 |
| หนัก 6-7 วัน/สัปดาห์ | 1.725 |
| หนักมาก/งานใช้แรง | 1.9 |

| เป้าหมาย | ค่าปรับ |
| --- | --- |
| ลดน้ำหนัก (ราว 0.5 กก./สัปดาห์) | −500 kcal |
| รักษาน้ำหนัก | 0 |
| เพิ่มน้ำหนัก | +400 kcal |

เป้าหมายจะไม่ต่ำกว่าค่าขั้นต่ำที่ปลอดภัย (ชาย 1,500 kcal, หญิง 1,200 kcal)

## เปิดใช้งานในเครื่อง

```bash
git clone https://github.com/sinenaruemon/calorie-program.git
cd calorie-program
```

จากนั้นดับเบิลคลิกไฟล์ `index.html` เพื่อเปิดในเบราว์เซอร์

## เผยแพร่ด้วย GitHub Pages

1. push ไฟล์ `index.html` ขึ้น branch `main`
2. ไปที่ **Settings → Pages** ของ repository
3. ในหัวข้อ **Build and deployment** เลือก **Deploy from a branch** เลือก `main` และ `/ (root)` แล้วกดบันทึก
4. รอสักครู่ แอพจะเปิดใช้ได้ที่ `https://sinenaruemon.github.io/calorie-program/`

## หมายเหตุ

- แคลอรี่ของอาหารเป็นค่าประมาณต่อ 1 จาน/ชิ้น ค่าจริงต่างกันไปตามร้านและปริมาณ
- ผลลัพธ์เป็นเพียงการประมาณ **ไม่ใช่คำแนะนำทางการแพทย์** หากมีโรคประจำตัวหรือตั้งครรภ์ ควรปรึกษาแพทย์หรือนักโภชนาการ
- ข้อมูลเก็บในเบราว์เซอร์ จึงอยู่เฉพาะเครื่องและเบราว์เซอร์นั้น หากล้างข้อมูลเว็บไซต์ ประวัติจะหายไป
