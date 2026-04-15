# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600503
**Name:** Võ Thành Danh
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | "Based on my data, the best choice is Laptop at $1200." | 9 | Correct product, reasonable price after ETL validation |
| Garbage Data (`garbage_data.csv`) | "Based on my data, the best choice is Nuclear Reactor at $999999." | 1 | Extreme outlier caused completely wrong recommendation |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung garbage data, Agent da tra loi sai vi du lieu chua nhieu van de chat luong nghiem trong. Thu nhat, co Duplicate ID (id=1 xuat hien hai lan cho ca Laptop va Banana), khien du lieu bi lon xon va khong nhat quan. Thu hai, co gia tri sai kieu du lieu: gia cua "Broken Chair" la chuoi "ten dollars" thay vi so, lam cho phep so sanh gia tro nen khong chinh xac. Thu ba, va nghiem trong nhat, la outlier cuc doan: "Nuclear Reactor" co gia 999999 USD - mot gia tri phi thuc te hoan toan. Vi Agent su dung logic tim san pham co gia cao nhat trong danh muc electronics, no chon Nuclear Reactor va dua ra khuyen nghi vo nghia. Cuoi cung, co Null values (id va category la None) cho "Ghost Item", tao ra cac ban ghi khong hop le. Tat ca nhung van de nay cho thay rang khi du lieu dau vao khong duoc kiem tra va lam sach, bat ky mo hinh hay he thong nao cung se cho ra ket qua sai, du logic xu ly co dung den dau.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y.

Du prompt co duoc viet tot den dau, neu du lieu dau vao chua day outlier, null values, duplicate IDs va sai kieu du lieu, Agent van se tra loi sai. Trong thi nghiem nay, cung mot cau hoi va cung mot logic, nhung Clean Data cho ket qua hop ly (Laptop - $1200) trong khi Garbage Data cho ket qua phi thuc te (Nuclear Reactor - $999999). Dieu nay chung minh rang data quality la nen tang cua moi he thong AI: "Garbage in, garbage out."
