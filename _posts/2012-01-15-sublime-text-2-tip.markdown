---
layout: post
title: 'Sublime Text 2 小技巧：開啓Browser'
date: 2012-01-15 05:30:00
categories: Tools osx
---

# Open In Browser 設定

### Step 1
開啓Preferences -> Browse Packages...


### Step 2
在HTML目錄底下建立<code>OpenBrowserCommand.py</code>檔案

程式碼貼入

{% highlight python %}
import sublime, sublime_plugin
import webbrowser

class OpenBrowserCommand(sublime_plugin.TextCommand):
   def run(self,edit):
      url = self.view.file_name()
      webbrowser.open_new(self.view.file_name())
{% endhighlight %}

### Step 3
在編輯HTML檔案時，<code>Ctrl</code> + <code>P</code> 開啓指令列
輸入 

{% highlight json %}
view.run_command('open_browser')
{% endhighlight %}

### 其他

這邊小小記錄一下相關的小技巧，另外其實這個技巧可以找到其他文章是FOR開啓PHP等
但因為小弟沒有這個需求，單純因為測試HTML每次都要打開Broswer點兩下感到不舒服＝ ＝
