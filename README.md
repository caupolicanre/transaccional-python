<a href="https://envialosimple.com/transaccional"><img src="https://envialosimple.com/images/logo_tr.svg" width="200px"/></a>

# EnvíaloSimple Transaccional - Python SDK

## Requirements

- Python 3.8 or higher
- EnvíaloSimple Transaccional API Key ([Create a demo account for free here](https://envialosimple.com/transaccional))

## Installation

```bash
pip install envialosimple-transaccional
```

## Basic Usage

```python
from envialosimple.transaccional import Transaccional
from envialosimple.transaccional.mail import MailParams

estr = Transaccional(your_api_key)

params = MailParams(
        from_email='no-reply@mycompany.com', 
        from_name='MyCompany Notifications',
        to_email='john.doe@example.com', 
        to_name='John Doe',
        reply_to='reply@here.com',
        subject='This is a test for {{name}}', 
        preview_text='A glimpse of what comes next...',
        html='<h1>HTML emails are cool, {{name}}</h1>', 
        text='Text emails are also cool, {{name}}',
        context={'name': 'John'})

estr.mail.send(params)
```

## Multiple Recipients Usage

```python
from envialosimple.transaccional import Transaccional
from envialosimple.transaccional.mail import MailParams

estr = Transaccional(your_api_key)

params = MailParams(
        from_email='no-reply@mycompany.com', 
        from_name='MyCompany Notifications',
        to_email=[
                {"email": 'jane.doe@example.com', "name": 'Jane Doe'},
                {"email": 'sean.smith@example.com', "name": 'Sean Smith'},
                {"email": 'john.doe@example.com'}
        ], 
        reply_to='reply@here.com',
        subject='This is a test for {{name}}', 
        preview_text='A glimpse of what comes next...',
        html='<h1>HTML emails are cool, {{name}}</h1>', 
        text='Text emails are also cool, {{name}}',
        context={'name': 'John'})

estr.mail.send(params)
```
