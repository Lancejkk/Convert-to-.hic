# MAP ⇄ HIC Conversion Toolkit

Scripts for converting between `.map` and `.hic` formats and combining two Hi-C maps, built around **Juicer Tools**.

## Requirements

- **Java JDK 1.7 or 1.8**  
  Download: <http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html>  
  (Ubuntu/LinuxMint alternative: <http://tecadmin.net/install-oracle-java-8-jdk-8-ubuntu-via-ppa/>)  
  Minimum system requirements for Java: <http://java.com/en/download/help/sysreq.xml>

- **Juicer Tools (latest .jar)**  
  <https://github.com/aidenlab/juicer/wiki/Download>

- **Python 3.9** (example environment)  
  Dependencies: `numpy`, `pathlib`  
  Install:
  ```bash
  pip install numpy pathlib
  ```

- **Scripts**
  - `converse_to_hic.py` (currently supports **1169×1169**; adjust if your map size/format differs)  
    <img width="776" height="52" alt="image-20250512144059609" src="https://github.com/user-attachments/assets/f2a58f87-86e5-452f-a498-3d0a781b58d7" />
  - `Convert_map_to_hic/convert_map_to_hic.py`
  - `convert_from_hic_to_csv.py`
  - `Combine_2hic.py`

- **Input map files** (processed **one at a time** for now)

---

## Usage

### 1) `.map → .hic`

1. Open `Convert_map_to_hic/convert_map_to_hic.py` and edit **`MAP_FILES`** (marked in the screenshot).  
   <img width="936" height="616" alt="image-20250512144920611" src="https://github.com/user-attachments/assets/ad2b3f47-928b-415e-9f9e-abad8ddbefa1" />
2. Run the script to generate the `.hic` file.

> Note: If your input format/size differs, update `converse_to_hic.py` accordingly.

---

### 2) `.hic → .csv (.map)`

1. Open the `.hic` in **Juicebox** to identify chromosome range and bin size (e.g., `chr11:1–122,082,543`, `Bin Size: 250 kb`, `Norm = None`).  
2. Use **juicer_tools** to dump the observed matrix (example):
   ```bash
   java -jar Tools/juicer_tools_1.22.01.jar dump observed NONE      "E:/chro_research/Week10/mouse_Big_hicmap/cellnames_cluster_4.hic"      chr11:1:122082543 chr11:1:122082543 BP 250000      mouse_cluster4_chr11_250kb.txt
   ```
3. Use the generated `.txt` as input to `convert_from_hic_to_csv.py`.
4. Run `convert_from_hic_to_csv.py` to obtain the `.csv` (or `.map`) file.

---

### 3) Combine two `.hic` maps into one view

- Set the correct paths in `Combine_2hic.py` and run.  
- Combining **without normalization** is supported.

---

## Reference

- Juicer tool command list: <https://github.com/aidenlab/juicer/wiki/Pre>
