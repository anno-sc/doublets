# anno-sctools
## QC
### doublets

* **module**: QC
* **toolname**: doublets
* **interpreter**: python3
* **program**: doublets.py

This script is for detect doublets from cellranger single cell gene expression raw matrix of one sample

### 依赖的包
依赖以下python包

1. [scrublet](https://github.com/AllonKleinLab/scrublet)
2. [DoubletDetection](https://github.com/JonathanShor/DoubletDetection) 

安装[scrublet](https://github.com/AllonKleinLab/scrublet)时遇到`cannot import name '_validate_lenghs'`的解决办法：[numpy兼容性报错修复](https://mp.weixin.qq.com/s/XfrvPEzANuuHFlLv34c5nA)

### 调用的方法/包

1. `scrublet`: https://github.com/AllonKleinLab/scrublet
2. `DoubletDetection`: https://github.com/JonathanShor/DoubletDetection 
3. `scrublet` and `DoubletDetection`
### 方法介绍

* https://mp.weixin.qq.com/s/XfrvPEzANuuHFlLv34c5nA
* https://mp.weixin.qq.com/s/b9NiL5NdiG5QMret5m-RXw

### usage
#### 参数介绍

* `-i` : inDir, one sample matrix.mtx, barcodes.tsv, genes.tsv files in the dir
* `-o` : output dir
* `-s` : output file prefix
* `-m` : select method to detect doublets, default scrublet_doubletdetection
* `-edr` : scrublet.Scrublet expected_doublet_rate, 采用程序默认值即可
* `-sdr` : scrublet.Scrublet sim_doublet_ratio, 采用程序默认值即可

##### 通过tools调用
`/path/tools QC doublets -i /path/sampledir -s sample1 -o /path/outDir`
##### 直接使用程序
`python3 doublets.py -i /path/sampledir -s sample1 -o /path/outDir`

#### 输出介绍

* `sample1_scrublet_doubletdetection_mark_doublets_barcodes.csv`：两种算法标记的每个barcode是否双细胞
* sample1_scrublet_doublet_score_histogram.pdf：scrublet算法doublet打分值分布
* sample1_scrublet_UMAP.pdf：scrublet算法双细胞在UMAP图上的分布
* sample1_doubletdetection_convergence.pdf：doubletdetection中间文件


