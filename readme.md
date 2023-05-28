# Basic TOML Tutorial

## Comments

- "#" is used for comments

## Syntax

- Key = Value

## Tables / Dictionary

- in order to create a table u have to give it a name with '[]'.
- a table is basically a group
  e.g.:

```
[itme-1]
name="abcd"
numbers=[1,2,3]
letters=['a','b','c']
padding=2
descriptions="This will execute the module no. 1"

[itme-2]
name="efgh"
numbers=[4,5,6]
letters=['e','f','g']
padding=2
descriptions="This will execute the module no. 2"
```

- It will look like this in the form of a Dictionary:

```
item-1: {'name':"abcd",
    numbers':[1,2,3],
    'letters':['a','b','c'],
    'padding':2,
    'descriptions':'This will execute the module no. 1'
}
```

## Creating a subtable

```
[item-1.details]
updated=true
author="John Conner"
```

- It will look like this in the form of a Dictionary:

```
item-1: {'name':"abcd",
    numbers':[1,2,3],
    'letters':['a','b','c'],
    'padding':2,
    'descriptions':'This will execute the module no. 1'
    'details':{
        'updated':true,
        'author':'John Conner'
    }
}
```

- Another Important example:

```
[database]
file.type='sqline'
file.path='data.db'
```

- It will look like this in the form of a Dictionary:

```
'database':{'file':{'type':ture,'path':'data.db'}}
```

## A Final Example:

```
# File Name : Config.toml

name="My project"
version='2.9.2'
website="https://example.com"

# output: {'name':"My project", 'version':'2.9.2', 'website':'https://example.com'}

[items]

numbers=[1,2,3]
letters= ['a','b','c']

# output:
{
    'name':"My project",
    'version':'2.9.2',
    'website':'https://example.com',
    'items':{
        'numbers':[1,2,3],
        'letters':['a','b','c']
    }
}

[items.details]

update=true
author="Nerdy Guy"

# output:
{
    'name':"My project",
    'version':'2.9.2',
    'website':'https://example.com',
    'items':{
        'numbers':[1,2,3],
        'letters':['a','b','c'],
        'details':{
            'update':true,
            'author':'Nerdy Guy'
        }
    }
}

[database]

file.type='sqlite'
file.path='data.db'

# output:
{
    'name':"My project",
    'version':'2.9.2',
    'website':'https://example.com',
    'items':{
        'numbers':[1,2,3],
        'letters':['a','b','c'],
        'details':{
            'update':true,
            'author':'Nerdy Guy'
        }
    }
    'database':{
        file:{
            'type':'sqlite',
            'path':'data.db'
        }
    }
}

# Creates an inline table

[inline_table]
inline={name="Nerdy Guy", age=30}

[[table_list]]
fruit='apple'

[[table_list]]
fruit='orange'

[[table_list]]
fruit='banana'

# output:
{
    'name':"My project",
    'version':'2.9.2',
    'website':'https://example.com',
    'items':{
        'numbers':[1,2,3],
        'letters':['a','b','c'],
        'details':{
            'update':true,
            'author':'Nerdy Guy'
        }
    },
    'database':{
        file:{
            'type':'sqlite',
            'path':'data.db'
        }
    },
    'table_list':[{'fruit':'apple'},{'fruit':'orange'},{'fruit':'banana'}]
}
```
