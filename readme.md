# SPREAD Scanner - Инструкция по подключению Firebase

##  Описание

Приложение может работать **как с Firebase, так и без него**:
- **Без Firebase**: все данные сохраняются в localStorage браузера (работает как статика)
- **С Firebase**: список rugpull монет синхронизируется между устройствами

---

## 🔧 Шаг 1: Создание проекта в Firebase

1. Перейди на [Firebase Console](https://console.firebase.google.com/)
2. Нажми **"Add project"** (Добавить проект)
3. Введи название проекта (например: `spread-screener`)
4. Отключи Google Analytics (не обязательно)
5. Нажми **"Create project"**

---

## 🔧 Шаг 2: Создание Realtime Database

1. В левом меню выбери **"Build"** → **"Realtime Database"**
2. Нажми **"Create database"**
3. Выбери расположение (рекомендуется `us-central1` или ближайшее к тебе)
4. Выбери **"Start in test mode"** (для начала)
5. Нажми **"Enable"**

---

## 🔧 Шаг 3: Настройка правил безопасности

1. В Realtime Database перейди на вкладку **"Rules"**
2. Замени правила на следующие:

```json
{
  "rules": {
    "spreads": {
      ".read": true,
      ".write": true
    }
  }
}