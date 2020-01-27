# login_ui_challenge

<img src="https://user-images.githubusercontent.com/41305917/73152383-69c73d00-40d8-11ea-9e3f-e018b26bb843.jpg" alt="Login screen design" width="240px" height="480px">

```
import 'package:flutter/material.dart';

class LoginScreen extends StatefulWidget {
  LoginScreen({Key key}) : super(key: key);

  @override
  _LoginScreenState createState() => _LoginScreenState();
}

class _LoginScreenState extends State<LoginScreen> {
  final _formKey = GlobalKey<FormState>();

  var _value = 1;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      resizeToAvoidBottomInset: false,
        backgroundColor: Colors.white,
        body: Stack(
          children: <Widget>[
            Positioned(
              top: 32.0,
              right: -50.0,
              child: Row(
                children: <Widget>[
                  circleContainer(25),
                  circleContainer(50),
                ],
              ),
            ),
            Positioned(
              top: 64.0,
              left: 16.0,
              child: Text(
                'Login',
                style: TextStyle(
                  fontWeight: FontWeight.bold,
                  fontSize: 42.0,
                ),
              ),
            ),

            Positioned(
              bottom: 64.0,
              right: 16.0,
              child: Text(
                'Sign Up',
                style: TextStyle(
                  fontWeight: FontWeight.bold,
                  fontSize: 42.0,
                ),
              ),
            ),
            Positioned(
              bottom: 32.0,
              left: -50.0,
              child: Row(
                children: <Widget>[
                  circleContainer(50),
                  circleContainer(25),
                ],
              ),
            ),
            Center(
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.center,
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: <Widget>[
                    Container(
                      margin: EdgeInsets.all(16.0),
                      padding: EdgeInsets.all(16.0),
                      decoration: BoxDecoration(
                          borderRadius: BorderRadius.circular(4.0),
                          boxShadow: [
                            BoxShadow(
                              color: Colors.deepPurple[200],
                              blurRadius: 16.0,
                            ),
                          ],
                          color: Colors.white),
                      height: MediaQuery.of(context).size.width / 2,
                      width: MediaQuery.of(context).size.width * 0.75,
                      child: Form(
                        key: _formKey,
                        child: Column(
                          mainAxisAlignment: MainAxisAlignment.spaceAround,
                          children: <Widget>[
                            buildTextFormField(
                                icon: Icons.person,
                                hint: "username",
                                obsecure: false),
                            buildTextFormField(
                                icon: Icons.lock, hint: "password", obsecure: true),
                          ],
                        ),
                      ),
                    ),
                    Row(
                      mainAxisAlignment: MainAxisAlignment.spaceBetween,
                      children: <Widget>[
                        Row(
                          children: <Widget>[
                            Radio(
                              value: 1,
                              groupValue: _value,
                              onChanged: (var v) {
                                setState(() {
                                  _value =v;
                                });
                                print(v);
                              },
                              activeColor: Colors.deepPurple,
                              autofocus: true,
                              focusColor: Colors.deepPurple,
                            ),

                            Text('Remember me',style: TextStyle(fontWeight: FontWeight.w700),),
                          ],
                        ),
                        Container(
                          alignment: Alignment.center,
                          height: 40.0,
                          width: 100,
                          decoration: BoxDecoration(
                            borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(32.0),
                                topLeft: Radius.circular(32.0)),
                            color: Colors.deepPurple,
                          ),
                          child: Text(
                            'Login',
                            style: TextStyle(color: Colors.white, fontSize: 21.0),
                          ),
                        )
                      ],
                    ),
                  ],
                )),
          ],
        ));
  }

  TextFormField buildTextFormField(
      {IconData icon, String hint, bool obsecure}) {
    return TextFormField(
      cursorColor: Colors.deepPurple,
      obscureText: obsecure,
      decoration: InputDecoration(
        hintText: hint,
        prefixIcon: Icon(
          icon,
          color: Colors.deepPurple,
        ),
        focusedBorder: UnderlineInputBorder(
            borderSide: BorderSide(color: Colors.deepPurple)),
        border: UnderlineInputBorder(
            borderSide: BorderSide(color: Colors.deepPurple)),
      ),
    );
  }

  Container circleContainer(double radius) {
    return Container(
      margin: EdgeInsets.all(8.0),
      height: radius * 2,
      width: radius * 2,
      decoration: BoxDecoration(
        borderRadius: BorderRadius.circular(radius),
        boxShadow: [
          BoxShadow(
            color: Colors.deepPurple[500],
            blurRadius: 8.0,
          ),
        ],
        color: Colors.deepPurple,
      ),
    );
  }
}

```

- ### [Design source](https://www.uplabs.com/posts/login-screen-mockups-design)

