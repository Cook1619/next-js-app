---
title: "Mapping Data to Components in React"
date: "2020-06-08"
---

Say we have our json which will mock an api call that looks like this
```json
const emojipedia = [
  {
    id: 1,
    emoji: "💪",
    name: "Tense Biceps",
    meaning:
      "“You can do that!” or “I feel strong!” Arm with tense biceps. Also used in connection with doing sports, e.g. at the gym."
  },
  {
    id: 2,
    emoji: "🙏",
    name: "Person With Folded Hands",
    meaning:
      "Two hands pressed together. Is currently very introverted, saying a prayer, or hoping for enlightenment. Is also used as a “high five” or to say thank you."
  },
  {
    id: 3,
    emoji: "🤣",
    name: "Rolling On The Floor, Laughing",
    meaning:
      "This is funny! A smiley face, rolling on the floor, laughing. The face is laughing boundlessly. The emoji version of “rofl“. Stands for „rolling on the floor, laughing“."
  },
];

export default emojipedia;
```

And we want to iterate over this data into a component from our app component
```jsx
import React from "react";
import emojipedia  from '../emojipedia';
import Entry from './Entry';

function App() {
  console.log(emojipedia)
  return (
    <div>
      <h1>
        <span>emojipedia</span>
      </h1>

      <dl className="dictionary">
        {emojipedia.map((e) => {
          return <Entry emoji={e.emoji} meaning={e.meaning} name={e.name} key={e.id} />
        })}
      </dl>
    </div>
  );
}

export default App;
```
### We are bringing in our json object and interating over the properties in each object and passing them to the Entry component

### This is what our entry component would look like
```jsx
import React from "react";

const Entry = (props) => {
  const { emoji, name, meaning } = props
  return (
    <div className="term">
      <dt>
        <span className="emoji" role="img" aria-label="Tense Biceps">
          { emoji }
        </span>
        <span>{ name }</span>
      </dt>
      <dd>
        { meaning }
      </dd>
    </div>
  );
};

export default Entry;

```