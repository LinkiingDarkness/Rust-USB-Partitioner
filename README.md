# Rust USB Partitioner (RustPRT)

RustPRT is a Windows tool for preparing USB drives to boot a Rust-based operating system with the [Limine](https://limine-bootloader.org/) bootloader.

It allows you to:

- Create new **FAT32** partitions from free or shrinkable space.
- Mark partitions as **EFI System Partitions (ESP)** for UEFI boot.
- Keep partitions **Explorer-visible** (assigning usable drive letters).
- Copy a **Rust kernel** binary and necessary **Limine files** onto the prepared partition.
- Optionally deploy for **BIOS/Legacy boot** (if Limine BIOS files are available).
- Manage partitions (create, delete, shrink, expand).

> ⚠️ **Warning:** This tool manipulates partitions directly. Data loss is possible if used incorrectly. Always back up your data before use.

---

## Requirements

- Windows 10 or later
- Administrator privileges (UAC prompt on launch)
- [Limine binary release](https://github.com/limine-bootloader/limine/releases)
- A Rust kernel build (ELF format)

---

## Features

- ✅ GUI built with Tkinter (no console window in packaged .exe)  
- ✅ Auto-shrink NTFS partitions to free space if needed  
- ✅ Force Explorer visibility for partitions  
- ✅ Automatic copying of kernel + Limine files  
- ✅ Write a default `limine.cfg` if requested  

---

## Usage

1. Build your Rust kernel (`cargo build --release`).
2. Download and extract Limine binaries.
3. Launch **RustPRT.exe** (run as Administrator).
4. Select your **Rust kernel** and **Limine folder**.
5. Create or select a partition.
6. Press **Prepare on Selected Partition** to set it up.

---

## Development

Clone the repo and run the Python script directly:

```bash
python flash_vacuum_partition.py
