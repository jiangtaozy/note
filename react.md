- set innerHTML img max-width

      import { css } from 'glamor';
      css.insert('img { max-width: 100%}')

- create-react-app Environment Variables

      npm start: process.env.NODE_ENV == 'development'
      npm build: process.env.NODE_ENV == 'production',
      npm test: process.env.NODE_ENV == 'test',

      // There is also a special built-in environment variable called NODE_ENV.
      // You can read it from process.env.NODE_ENV.  When you run npm start,
      // it is always equal to 'development', when you run npm test it is always
      // equal to 'test', and when you run npm run build to make a production
      // bundle, it is always equal to 'production'.

- Uncaught TypeError: Cannot read property '__reactInternalInstance$foyrksc2xe4' of null

      If you have an error like this, you likely have an earlier error which got React into an inconsistent state.

- Uncaught (in promise) Invariant Violation: You must specify the "to" property

      <Link to='' ></Link> // to='' will result in error

- Custom Environment Variables

    // package.json
    "scripts": {
      "start": "REACT_APP_SECRET_CODE=http://192.168.31.10 node scripts/start.js",
    },
    // App.js
    console.log(process.env.REACT_APP_SECRET_CODE)

- React-router go to same path not reload bug
    componentDidUpdate(prevProps, prevState, snapshot) {
      const { match: { params: { id } } } = this.props;
      const { match: { params: { id: prevId } } } = prevProps;
      if(id !== prevId) {
        this.setState({
          addPage: !id,
        });
        const { form } = this.props;
        form.resetFields();
      }
    }

- Create react app using https in development

      HTTPS=true npm start // not in fish
