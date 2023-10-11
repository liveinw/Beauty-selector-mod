# Beauty_selector
> 可以在游戏中一键切换特写美化或人模美化的mod助手。
>
> 该mod需要helper器和loader器进行辅助。（最后一步放连接）
>
> **只有特写创作者需要用到helper**，普通使用者只需要loader和Beauty_selector，直接去看5.loader加载mod教程

---

使用方法：

1. 这个mod对 `img ` 内的图片文件根据属于 `特写美化` 还是 `人模美化` 进行了分类，**注意衣物(clothes/)相关的差别**

特写 **closeup**：

```
/face/
/hair/
/body/basehead
/body/cum/Face 1,2 & /body/cum/Face 3,4 & /body/cum/Face 5  **脸部精液**
/clothes/head **帽子**
/clothes/???/back.png  **显示在背后的衣物，例如修女帽的背面**
/transformations/
```

人模 **bodystyle**：

```
/body
/hair/phair
/clothes
/clothes/face 	**注意面部饰品只能跟着人模走**
```



2. 在 `boot.json ` 文件根据 1. 填写你导入的img文件属于哪一类的美化，替换{mod_name}为你的美化名

   人模美化 **bodystyle**：

   ```
   {
   	"TODO": "options.twee",
   	"passageName": "Options Overlay",
   	"from": "<span class=\"gold\">美化选择</span><br>",
   	"to": "<span class=\"gold\">美化选择</span><br>\n\t<label><<radiobutton \"$options.bodystyle\" \"{mod_name}\" autocheck>> {选项-主题里显示的名字}</label> | <br>"
   }
   ```

   拿`beeesss`举例，

   ```
   {
       "TODO": "options.twee",
       "passageName": "Options Overlay",
       "from": "<span class=\"gold\">美化选择</span><br>",
       "to": "<span class=\"gold\">美化选择</span><br>\n\t<label><<radiobutton \"$options.bodystyle\" \"bee\" autocheck>> BEE</label> | <br>"
                  }
   ```

​	脸部特写  **closeup**:

```
{
	"TODO": "options.twee",
	"passageName": "Options Overlay",
	"from": "<span class=\"gold\">美化选择</span><br>",
	"to": "<span class=\"gold\">美化选择</span><br>\n\t<label><<radiobutton \"$options.closeup\" \"{mod_name}\" autocheck>> {选项-主题里显示的名字}</label> | <br>"
}
```

> **提醒** : 第一行的name记得改成你的mod名字，所有的{}都是你要替换的，最后boot里不会有任何中文字，如果同时有bodystyle和closeup，就打一个逗号（英文的）然后复制粘贴上面的代码（twee里只有两个{}之间有，不要在最后一个{}的后面写，）



3. 下载helper，放入`mods`文件夹，在 `mods` 里的 `img` 文件夹里根据 1. 的分类建立所需要的 `body`、`face`、`hair` 、`clothes` 文件夹，再在该文件下建立以你的 {mod_name} 命名的文件夹，再把你的美化文件放进去

   文件目录最后如下：

   ```
   mods
    ├── {mod_name}
    │    ├── boot.json <你需要编写代码的地方>
    │    └── img 
    │    	   ├── face (如果有)
    │    	   		└── {mod_name} ({mod_name}里面再建你美化的文件夹)
    │    	   └── hair (如果没画可以从pb或原版搬能用的png放着，不然找不到图会报错)
    │    	   		└── {mod_name} ({mod_name}里面再建你美化的文件夹)
    │    	   ├── body (如果有)
    │    	   		└── {mod_name} ({mod_name}里面再建你美化的文件夹)
    │    	   └── clothes (如果没画可以从pb或原版搬能用的png放着，不然找不到图会报错)
    │    	   		└── {mod_name} ({mod_name}里面再建你美化的文件夹)
    │    	   			  ├── upper (举例)
    │					  ...
    ...
   ```

   

4. 最后，在helper下的根目录（有main.py的）的资源路径导航栏（就是那个显示文件夹目录名字的框）输入

   ```
   cmd
   ```

   在弹出的黑框输入代码按下ENTER，

   ```
   pip install -r requirements.txt
   ```

   ```python
   python -m main
   ```

   等他运行完，你helper下的results文件里会出现一个zip文件，那个就是你用于loader的mod包了。

   

5. 打开loader里的html文件，在左下角有个 `Mod管理器` 点击它，依次点击执行以下操作：

   选择文件-双击mod包-添加旁加载Mod-重新载入。

   加载顺序：i18n => Beauty-selector => 想要的美化.zip

   然后就可以开始游戏了。

   > 手机就随便找个包替换掉img文件和html。
   >
   > 想导入汉化（i18n.zip）也是同样的步骤。
   >
   > 如果要移除某个mod包，就在Mod管理器里找出你要移除的mod然后点他旁边那个按钮移除。

   

6. 写好模板的helper器链接，原作者（Number_Sir）：

   https://github.com/NumberSir/DOL-Mod-Created-Helper

   打包好的loader器+汉化包（i18n.zip），原作者（Lyoko-Jeremie）：

   https://github.com/suin14/Beauty_selector_helper

   仓库里有打包好的bee+paril美化做例子（只是写mod的测试用例，不保证使用）

   beauty-selector美化转换器发布仓库：

   https://github.com/suin14/Beauty_selector_helper

   **需要挂梯子，github怎么下载文件不需要我教了吧orz**



**实在真的搞不懂再找作者**

QQ：3042931495 猫猫教传教士
