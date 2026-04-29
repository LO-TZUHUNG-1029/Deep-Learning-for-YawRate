# Deep-Learning-for-YawRate
NTU Racing Team Project

操作步驟:

解壓縮打開 DeepLearningforYawRate 資料夾 > 打開 LSTM_YawRate.m 和 LSTM_YawRate_test.m

檢查 LSTM_YawRate 中第四行:

fileList = { ...
    "C:\Users\lojac\Desktop\NTU_RACING\tv試車數據\DeepLearningforYawRate\0322 _test\can_log_vcu_20260322_161755_decoded.csv"
    "C:\Users\lojac\Desktop\NTU_RACING\tv試車數據\DeepLearningforYawRate\0322 _test\can_log_vcu_20260322_162117_decoded.csv"
    "C:\Users\lojac\Desktop\NTU_RACING\tv試車數據\DeepLearningforYawRate\0322 _test\can_log_vcu_20260322_162445_decoded.csv"
};

找到資料夾中0322_test或其他要拿來訓練的數據複製檔案路徑到上面，要注意csv檔中的數據"行"位置，不確定可以看下面提取特徵的部分


完成檢查後，按Run開始訓練
