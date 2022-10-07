- 注释

      # 这是一个注释
      '''
      这是多行注释，用三个单引号
      '''
      """
      这是多行注释，用三个双引号
      """

- zipfile 中文乱码问题

      打开/usr/lib64/python3.7/zipfile.py
      搜索cp437，修改为

      #filename = filename.decode('cp437')
      try:
          filename = filename.decode('utf-8')
      except:
          filename = filename.decode('gbk')

      #fname_str = fname.decode("cp437")
      try:
          fname_str = fname.decode('utf-8')
      except:
          fname_str = fname.decode('gbk')

- 打印对象

      print(obj.__dict__)

- 安装pytesseract

      sudo dnf install libtool
      download leptonica
      https://github.com/DanBloomberg/leptonica/releases
      ./configure
      make
      sudo make install
      git clone --depth 1  https://github.com/tesseract-ocr/tesseract.git
      cd tesseract
      ./autogen.sh
      #export LD_LIBRARY_PATH=/usr/local/lib/
      export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig/
      ./configure
      make
      sudo make install
      sudo ldconfig
      download tessdata to /usr/local/share/tessdata
      https://github.com/tesseract-ocr/tessdata/releases
      tesseract --list-langs
      pip install pytesseract

- 安装 cv2

      pip install opencv-python-headless

- 安装 skimage

      pip install scikit-image

- 打印更多qt信息

      export QT_DEBUG_PLUGINS=1

- 模板字符串

      >>> name = "Eric"
      >>> age = 74
      >>> f"Hello, {name}. You are {age}."
      'Hello, Eric. You are 74.'

- cv2 show plt

      from matplotlib import pyplot as plt
      plt.subplot(1, 4, 1)
      plt.imshow(gray, cmap='gray')
      plt.title('gray')
      plt.subplot(1, 4, 2)
      plt.imshow(thres, cmap='gray')
      plt.title('thres')
      plt.subplot(1, 4, 3)
      plt.imshow(morph_img, cmap='gray')
      plt.title('remove_line')
      plt.subplot(1, 4, 4)
      plt.imshow(remove_hole_img, cmap='gray')
      plt.title('remove_hole_img')
      plt.axis('off')
      plt.show()

- 遍历文件夹

      files = os.walk('/home/jemo/workspace/tieta/network-management-system/vcode')
      for path,dir_list,file_list in files:
          for img_file in file_list:
              print("img_file: ", img_file)
              vcode = recognize_vcode('vcode/' + img_file)

- 字符串替换

      str.replace(old, new[, max])

      str = "this is string example....wow!!! this is really string"
      print str.replace("is", "was")
      print str.replace("is", "was", 3)

- and

      if x > 3 and x < 10:
          print(x)

- 字典keys

      dict.keys()

- Python Tuples

      mytuple = ("apple", "banana", "cherry")

      A tuple is a collection which is ordered and unchangeable.
      Tuple items are ordered, unchangeable, and allow duplicate values.
      Tuple items are indexed, the first item has index [0], the second item has index [1] etc.

- for 循环

      fruits = ["apple", "banana", "cherry"]
      for x in fruits:
        print(x)
      for x in range(6):
        print(x)

- string

      Strings in python are surrounded by either single quotation marks, or double quotation marks.

      'hello' is the same as "hello".

- 打印字典

      import json
      dic = {
          "a": {
              "b": "c",
           },
      }
      print(json.dumps(dic, indent=4))

- 日期格式化

      this_month_first_day_str = datetime.strftime(this_month_first_day, '%Y-%m-%d')

- 昨天 yesterday

      from datetime import date, timedelta
      yesterday = date.today() - timedelta(days=1)
      yesterday.strftime('%m%d%y')


- request get params
      pcms_params = {
          "original_url": "/contractmgr/contractoper/ContractQuery.jsp",
          "token": token,
      }
      session.get(pcms_url, params=pcms_params)

- request post params

      payload = {
          "parentCd": "330000",
      }
      city_data = session.post(city_list_url, json=payload).json()

- requests post form data

      payload = {'key1': 'value1', 'key2': 'value2'}
      r = requests.post("https://httpbin.org/post", data=payload)

- get timestamp

      import time
      timestamp = round(time.time() * 1000)

- requests set headers

      session.headers.update({'x-test': 'true'})

- requests get cookies

      print(session.cookies.get_dict())

- flask run

      py -m flask run

- windows pip配置国内镜像源

      pip config set global.index-url http://mirrors.aliyun.com/pypi/simple/
      pip config set install.trusted-host mirrors.aliyun.com
