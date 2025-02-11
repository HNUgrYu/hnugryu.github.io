# pip install显示错误
ERROR: Could not find a version that satisfies the requirement python (from versions: none)

ERROR: No matching distribution found for python
## 删除代理配置
nano ～/.config/pip/pip.conf

# 桌面dock图标显示错乱
## desktop文件不应该放在桌面
mv ~/桌面/zotero.desktop ~/.local/share/applications/