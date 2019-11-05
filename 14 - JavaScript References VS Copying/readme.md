# Project 14 - References VS Copying

## Objective

Understanding the difference between Reference VS Copy

### JavaScript

With strings, numbers and booleans we can simply make a copy of by assigning it to an other variable.

```
let age = 100;
let age2 = age;
console.log(age, age2);
age = 200;
console.log(age, age2);
```

When it comes to arrays we can not simply make a copy of by assigned it to an other variable.

```
const players = ['Wes', 'Sarah', 'Ryan', 'Poppy'];
const team = players;
team[3] = 'Andy';
console.log('OUTPUT: team', team);
console.log('OUTPUT: players', players);
```

This will make a reference to the original array.

```
OUTPUT: team ["Wes", "Sarah", "Ryan", "Andy"]
OUTPUT: players ["Wes", "Sarah", "Ryan", "Andy"]
```

Ways to make a copy of arrays:

```
const team2 = players.slice();
const team3 = [].concat(players);
const team4 = [...players];
const team5 = Array.from(players);
```

This goes for the same for objects

```
const person = {
  name: 'Andy Nguyen',
  number: 26
};

const captain = person;
captain.name = 'Andrew Nguyen';
```

`person.name` will return 'Andrew Nguyen'

Ways to make a copy of an object:

```
const cap2 = Object.assign({}, person, { number: 99 });
const cap3 = { ...person };
```

Copying will only be 1 level deep. Both for Arrays and Objects.

```
const andy = {
  name: 'Andy',
  age: '26',
  social: {
    linkedin: 'andydnguyen',
    facebook: 'andynguyen904'
  }
};
```

```
const dev = Object.assign({}, person);

dev.social.linkedin = 'andy904'
```

`andy.social.linkedin` will also equal to 'andy904'

Look into cloneDeep method.

Possible to copy all the objects with `const dev2 = JSON.parse(JSON.stringify(andy));` but this is not recommended.
