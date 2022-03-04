-
- [[Metadata]]:
  [[Date]]: [[Feb 24th, 2022]] 
  [[Author]]:[[Kevin Song]]
  [[Reference links]]:None
  [[Status]]: [[DOING]]
  [[Keywords]]: #技术
	- [[Notes]]：
		- [[Question]]：logseq如何美化简悦的主题？
collapsed:: true
			- query-table:: false
			  ``` 简悦导出 Markdown 的 logseq主题
			  [[Metadata]]:  
			          - [[keywords]]: #[[SimpRead]] {{tags}}
			  [[Date Read]]: [[{{date_format|now|yyyy-MM-dd}} ]]
			                 - [[Notes]]:  
			  {{#each}}
			  {{                                       - >|an_html}}
			  {{                                        - |an_note}} 
			  
			  {{an_tags}}  [📌](<{{an_int_uri}}>) 
			  {{/each}}
			  ```
			  #简悦 #logseq
		-
		- [[Question]]：logseq如何美化后输出 github？
collapsed:: true
			- 通过在本地`..\kevin\document\logseq\page`  文件夹编辑`md`文件，然后拷贝至`..\kevin\document\ Github\knowledge-garden\page`中，然后 github  action会自动同步至github 中。具体样例见 简悦 + logseq + github page 无代码全自动化知识管理发布方案
			  #logseq
			-
		- [[Question]]:[[如何将本地图片上传图床？]]
-
-