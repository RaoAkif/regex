<h1 align="center"> REGEX </h1>

#### Removing `a-z`, `A-Z`, `0-9`
```
string = string.replace(/[a-z]/g, '')       //      Remove the small-caps chars
```
```
string = string.replace(/[A-Z]/g, '')       //      Remove the big-caps chars
```
```
string = string.replace(/[0-9]/g, '')       //      Remove the integers
```

#### Removing AlphaNumeric Chars ( Leaving only `a-z`, `A-Z`, `0-9` )
```
string = string.replace(/[^0-9a-zA-Z]/g, '')
```

#### Only Numbers
```
string = string.match(/[0-9]/g)
```

#### Only Alphabets
```
string = string.match(/[a-zA-Z]/g)
```


<p align="center">
    <img width="100%" src="https://user-images.githubusercontent.com/61361037/203317658-8f29c1a4-17c9-4dac-8c4a-83cc7c6d6528.png" alt="Material Bread logo">
</p>

