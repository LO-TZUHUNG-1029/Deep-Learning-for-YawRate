# Deep-Learning-for-YawRate
NTU Racing Team Project

操作步驟:

1.解壓縮打開 DeepLearningforYawRate 資料夾 > 打開 LSTM_YawRate.m 

2.檢查 LSTM_YawRate.m中第四行以下:

fileList = { ...

    "C:\Users\lojac\Desktop\NTU_RACING\tv試車數據\DeepLearningforYawRate\0322 _test\can_log_vcu_20260322_161755_decoded.csv"
    "C:\Users\lojac\Desktop\NTU_RACING\tv試車數據\DeepLearningforYawRate\0322 _test\can_log_vcu_20260322_162117_decoded.csv"
    "C:\Users\lojac\Desktop\NTU_RACING\tv試車數據\DeepLearningforYawRate\0322 _test\can_log_vcu_20260322_162445_decoded.csv"
    
};

找到資料夾中 0322_test資料夾 中的csv試車數據 或 其他要拿來訓練的csv數據 複製檔案路徑到上面，另外需要預留一筆未經訓練的數據來測試使用，要注意csv檔中的數據"行"位置，不確定可以看LSTM_YawRate.m下面"提取特徵"的部分，可以對一下每一行應該代表的數據名稱


3.完成檢查後，按Run開始訓練

 P.S. 這個機器學習所使用的為 Long Short-Term Memory (LSTM) ，以下為LSTM的Layer:

 layers = [ ...
 
    sequenceInputLayer(numFeatures)
    lstmLayer(numHiddenUnits, 'OutputMode', 'sequence')
    fullyConnectedLayer(64)
    reluLayer()
    fullyConnectedLayer(32)
    reluLayer()
    fullyConnectedLayer(16)
    reluLayer()
    dropoutLayer(0.2)
    fullyConnectedLayer(1)
    regressionLayer

    ];
LSTM 相關資訊可參考: 

https://tengyuanchang.medium.com/%E6%B7%BA%E8%AB%87%E9%81%9E%E6%AD%B8%E7%A5%9E%E7%B6%93%E7%B6%B2%E8%B7%AF-rnn-%E8%88%87%E9%95%B7%E7%9F%AD%E6%9C%9F%E8%A8%98%E6%86%B6%E6%A8%A1%E5%9E%8B-lstm-300cbe5efcc3
    
4.訓練完成後，開啟 LSTM_YawRate_test.m

5.檢查 LSTM_YawRate_test.m 中第8行:

test_data = readmatrix(

"C:\Users\lojac\Desktop\NTU_RACING\tv試車數據\DeepLearningforYawRate\0322 _test\can_log_vcu_20260322_162727_decoded.csv"

);

這裡的檔案路徑要放的是剛剛預留的那一筆未經訓練的csv數據，現在要在 LSTM_YawRate_test.m  中測試剛剛訓練的效果如何，同樣記得檢查這筆csv中的行是否正確

6.檢查後就可以按Run

7.跑完測試後會顯示出用訓練後預測的 YawRate 以及與實際數據比較後的 Error ，最後還有Correlation Plot 
