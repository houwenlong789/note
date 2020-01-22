### boll

- 初始化
 self.bollData = bt.indicators.BollingerBands(self.data, period=25)
- 获取boll 值数据  self.bollLines = self.bollData.lines
- 获取当前日期的中值 self.bollLines.mid.get()[0]
- 
