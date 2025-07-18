# 電子喉語音轉換綜合分析

## Abstract
本研究探討兩種電子喉語音——頸部電子喉（CEL）與鼻部電子喉（NEL）在語音轉換任務中的表現。CEL 為常見的替代發聲工具，但需將裝置貼於頸部使用，對於術後頸部傷口尚未癒合的喉切除患者而言，無法立即使用。相較之下，NEL 採用鼻腔傳導激勵訊號，不僅避開頸部接觸，更能降低震動噪音並穩定語音輸出，特別適用於術後早期患者。

本研究提出一系列轉換策略與訓練技術，包括：
* 使用 梅爾頻譜與WavLM 特徵進行比較
* 使用 VTN-VC 作為基線模型
* 設計 ETN-VC 模型，搭配資料擴增與特徵選擇以強化轉換品質
* 應用 局部線性嵌入（LLE-VC）與生成式文本擴增電子喉語料提升資料數量
* 探討 前處理與後處理的 Two-Stage VC 架構

實驗結果顯示：NEL 搭配 梅爾頻譜特徵與資料擴增策略，在語音自然度與理解度上表現最佳，優於基線 VTN-VC 模型與其他組合，也優於 CEL 在任何系統上的結果，突顯資料品質與特徵選擇的重要性。

## Objective evaluation

Intelligibility related:
* MCD: Mel-cepstrum distortion
* SER: syllable error rate of ASR system

F0 (Pitch) related:
* F0 RMSE: F0 root mean square error
* F0 CORR: F0 correlation coefficients

Duration related:
* DDUR: average absolute duration difference between the converted and target utterances

**sample 1**

|   Model   |transcription: 他捐了很多衣物給災區 (wo bang ta ba ji dan fang ru bing xiang)|
|:---------:|:-------------------------------------------------------------------:|
| EL speech | <audio src="audio/EL01v4/EL01_281.wav" controls preload></audio> |
| MT-CLDNN  | <audio src="audio/el01_nl02/mtcldnn/EL01-NL02_MTCLDNN_h5_GV_no0th_285.wav" controls preload></audio> |
|    TFS    | <audio src="audio/el01_nl02/tfs/EL01-NL02_TFS_285.wav" controls preload></audio> |
|    PT     | <audio src="audio/el01_nl02/pt/EL01-NL02_PT_285.wav" controls preload></audio> |
| NL speech | <audio src="audio/nl02/NL02_285.wav" controls preload></audio> |
