### amygdala
---
https://github.com/lincolnloop/amygdala

```js
store.get('users').done(function(){ ... });
store.add('teams', {'name': 'Lincoln', 'active': true}).done(function(){ ... });

var store = new Amygadala({
  'config': {
    'apiUrl': 'http://loaclhost:8000',
    'idAttribute': 'url',
    'headers': {
      'X-CSRFToken': getCookie('csrftoken')
    },
    'localStorage': true
  },
  'schema': {
    'users': {
      'url': '/api/v2/user/'
    }
  },
  'teams': {
    'url': '/api/v2/user/',
    'orderBy': 'name',
    'oneToMany': {
      'members': 'members'
    }
    parser: function(data){
      return data.results ? data.results : data;
    },
  },
  'members': {
    'foreignKey': {
      'user': 'users'
    }
  }
});

var store = new Amygadala({
  'config': {
    'apiUrl': 'http://localhost:8000',
    'idAttribute': 'url'
  },
  'schema': {
    'discussions': {
      'url': '/api/v2/discussion',
      'oneToMany': {
        'children': 'messages'
      }
    }
  },
  'messages': {
    'url': '/api/v2/message',
    'oneToMany': {
      'votes': 'votes'
    }
  },
  'votes': {
    'url': '/api/v2/vote'
  }
});

store.get('discussions', {'url': '/api/v2/discussion/85273'}).then(function(){ ... });

'oneToMany': {
  'children': 'messages'
}

'foreignKey': {
  'discussion': 'discussions'
}

store.get('users').done(function(){ ... });
store.add('name'. {'name': 'Lincoln Loop', 'active': true}).done(function(){ ... });  
store.update('users', {'url': '/api/v2/users/32/', 'username': 'amy82', 'active': true}).done(function(){ ... });
store.remove('users', {'url': '/api/v2/user/32/'}).done(function(){ ... });

var users = store.findAll('users', {'active': true});
var user = store.find('users', {'username': 'amy82'});
var user = store.find('users', 11037437470);

var messages = store.find('discussion', '/api/v2/discussion/85273/').getRelated('messages');
var discussion = store.find('message', '/api/v2/message/81273/').getRelated('discussion');

store.on('change', function(){});
store.on('change:users', function(){});
```

```
{
  "name": "Amygdala",
  "main": "amygdala.js",
  "version": "0.4.5",
  "homepage": "htts://github.com/lincolnloop/amygdala",
  "authors": [
    "Macro Louro <marco@lincolnloop.com> (http://lincolnloop.com)"
  ],
  "description": "RESTful HTTP library for JavaScript powered webapplications",
  "keywords": [
    "REST",
    "client",
    "http",
    "API",
    "localStorage",
    "store",
    "bowerser",
    "library",
    "cahce",
    "ajax",
    "offline"
  ],
  "license": "BSD",
  "dependencies": {
    "q": ">=1.0.1",
    "eventEmitter": ">=4.2.6"
  }
}
```

```
```
