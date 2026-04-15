[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573998&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600503
**Student Email:** vothanhdanh8208@gmail.com
**Name:** Võ Thành Danh

---

## Mo ta

Bai lab nay xay dung mot ETL Pipeline tu dong de xu ly du lieu san pham tu file JSON. Pipeline gom 4 buoc chinh: Extract (doc du lieu tu JSON), Validate (loai bo cac ban ghi khong hop le co gia <= 0 hoac category rong), Transform (tinh gia giam 10%, chuan hoa category thanh Title Case, them timestamp), va Load (luu ket qua ra file CSV). Ngoai ra, bai lab bao gom thi nghiem Stress Test de chung minh rang chat luong du lieu anh huong truc tiep den do chinh xac cua AI Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

Ket qua se duoc luu vao `processed_data.csv`.

### Tao Garbage Data
```bash
python generate_garbage.py
```

### Chay Agent Simulation (Stress Test)
```bash
python agent_simulation.py
```

Chay agent voi ca `processed_data.csv` (clean) va `garbage_data.csv` (garbage) de so sanh ket qua.

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── agent_simulation.py      # AI Agent simulation
├── generate_garbage.py      # Script tao garbage data
├── raw_data.json            # Du lieu dau vao
├── processed_data.csv       # Output cua ETL pipeline
├── garbage_data.csv         # Du lieu "rac" de stress test
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- **Tong so records dau vao:** 5
- **Records hop le (processed):** 3 (Laptop, Chair, Monitor)
- **Records bi loai bo:** 2 (Mystery Box co gia am, Phone co category rong)
- **Stress Test:** Clean data cho ket qua chinh xac (Laptop - $1200), Garbage data cho ket qua sai (Nuclear Reactor - $999999) do outlier cuc doan.
