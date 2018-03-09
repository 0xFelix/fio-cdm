# fio-cdm

Mimic CrystalDiskMark 6 on Linux devices with the help of fio

Tested with fio version 3.5

## Usage

```
fio-cdm <path>
```

If using a custom build fio change `FIOCMD` to the absolute path of the fio binary.


## Notes

Currently the following warning is emitted when running the script:

```
128K-Q32T1-Seq-Read: No I/O performed by libaio, perhaps try --debug=io option for details?
128K-Q32T1-Seq-Write: No I/O performed by libaio, perhaps try --debug=io option for details?
```

The results of the script seem to be correct but this should be investigated.
This probably has something to do with the `ramp_time` option.

### Sample

```
# fio-cdm /mnt/bc35
|           | Read(MB/s)|Write(MB/s)|
|-----------|-----------|-----------|
| Seq Q32T1 |    183.000|    148.000|
| 4K  Q8T8  |      1.114|      1.229|
| 4K  Q32T1 |      1.519|      0.888|
| 4K  Q1T1  |      0.621|      0.965|
```
