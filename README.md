# Emoji Platform Recognition via Transfer Learning

פרויקט סיום בקורס Deep Learning — מערכת המסווגת לאיזו פלטפורמה (Apple, Google, Samsung, Facebook, Windows, Twitter, JoyPixels) שייך אימוג'י נתון, באמצעות Transfer Learning ו-Pre-trained Models.

## מטרת הפרויקט

מחזור חיים מלא של פרויקט Deep Learning: קבלת נתונים גולמיים ורועשים ("Dirty Data"), ניקוי והרחבה (Data Cleaning, Data Augmentation), ואימון מודל קיים בשיטות Transfer Learning ו-Fine-Tuning.

## Dataset

Emoji Dataset — כל אימוג'י קיים ב-7 פלטפורמות שונות. התמונות התקבלו כ-Base64 ופוענחו לקבצי PNG.

## מבנה הנוטבוקים (לפי סדר הרצה)

| נוטבוק | מה הוא עושה |
|---|---|
| `02_data_processing.ipynb` | פענוח Base64, יצירת קבצי PNG, ארגון לפי תיקיות פלטפורמה |
| `03_data_cleaning.ipynb` | Duplicate Detection & Removal, Corrupted Files Check, Class Distribution לפני/אחרי ניקוי |
| `04_prepare_dataset.ipynb` | Train/Validation/Test Split, בניית Dataset ו-DataLoaders, הגדרת Data Augmentation |
| `05_baseline_model.ipynb` | מודל ResNet50 עם Transfer Learning (Pretrained Weights, Frozen Backbone) |
| `06_augmentation_experiment_v2.ipynb` | מודל EfficientNet-B0 עם Transfer Learning + Augmentation, Confusion Matrix מנורמל |
| `07_gap_closure_ablation.ipynb` | Mislabeled Data Detection, Outlier Detection, ו-Ablation Study מלא (4 שלבים: Baseline גולמי → Cleaning → Augmentation → Transfer Learning), כולל Test Accuracy אמיתי ו-Confusion Matrix לכל שלב |

## שיטה

1. **Architecture** — בחירת רשת קיימת (ResNet50 / EfficientNet-B0) וטעינת Pre-trained Weights
2. **Data Cleaning** — איתור ותיקון Mislabeled Data, הסרת כפילויות (למניעת Data Leakage), סינון Outliers ונתונים פגומים
3. **Data Augmentation** — טרנספורמציות (Flip, Rotation, ColorJitter) על קבוצת ה-Train בלבד, למניעת Overfitting
4. **Ablation Study** — השוואת Test Accuracy על פני 4 שלבי ניסוי, לבידוד התרומה של כל שיפור בנפרד

## תוצאות

*(להשלים לאחר סגירת כל הריצות — Test Accuracy סופי לכל שלב, אחוז שיפור, וממצאי Confusion Matrix)*

## הרצה

1. התקנת דרישות: `torch`, `torchvision`, `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `Pillow`
2. הרצת הנוטבוקים לפי הסדר בטבלה למעלה
3. הנתונים אמורים לשבת בתיקיית `../data/processed/` ביחס לתיקיית הנוטבוקים
