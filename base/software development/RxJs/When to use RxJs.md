
Code that deals with **more than one event** or **asynchronois computation gets complicated quickly** as it needs to build a state-machine to deal with ordering issues. Next to this, the code needs to deal with successful and failure termination of each seperate computation. This leads to code that doesn't follow normal control-flow, is hard to understand and hard to maintain.

**Sample**
```
var input = document.getElementById('input');
var dictionarySuggest = Rx.Observable.fromEvent(input, 'keyup')
  .map(() => input.value)
  .filter(text => !!text)
  .distinctUntilChanged()
  .throttle(250)
  .flatMapLatest(searchWikipedia)
  .subscribe(
    results => {
      list = [];
      list.concat(results.map(createItem));
    },
    err => logError(err)
  );
```

Reference:
1. [[Intro]]