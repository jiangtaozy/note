- post

      requests.post(url, data={key: value}, json={key: value}, args)

- json result


      requests.get(url).json()

- text result

      requests.get(url).text

- print headers

      print("session.headers: ", session.headers)

- update header

      session.headers.update({'User-Agent': user_agent})

- 相同参数

      多个相同参数名，不同的值。我们只需要把值定义成一个列表，传递给参数即可
      list = [1, 2, 3]
      data = {
          'key': list,
      }
      res = requests.post(url, data=data)
