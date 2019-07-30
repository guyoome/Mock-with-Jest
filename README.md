# Mock Jest
## Attributes

 - [_isMockFunction](#ismockfunction)
 - [getMockImplementation](#getmockimplementation)
 - [mock](#mock)
 - [mockClear](#mockclear)
 - [mockReset](#mockreset)
 - [mockRestore](#mockrestore)
 - [mockReturnValueOnce](#mockreturnvalueonce)
 - [mockResolvedValueOnce](#mockresolvedvalueonce)
 - [mockRejectedValueOnce](#mockrejectedvalueonce)
 - [mockReturnValue](#mockreturnvalue)
 - [mockResolvedValue](#mockresolvedvalue)
 - [mockRejectedValue](#mockrejectedvalue)
 - [mockImplementationOnce](#mockimplementationonce) 
 - [mockImplementation](#mockimplementation)
 - [mockReturnThis](#mockreturnthis)
 - [mockName](#mockname)
 - [getMockName](#getmockname)

### _isMockFunction
````javascript
const myMock = jest.fn();
myMock._isMockFunction;
````
> return a Boolean 
### getMockImplementation
````javascript
   () => this._ensureMockConfig(f).mockImpl
````
### mock
#### calls

````javascript
typeof myMock.mock.calls === Array()
````
#### instances
````javascript
typeof myMock.mock.instances === Array()
````
#### invocationCallOrder
````javascript
typeof myMock.mock.invocationCallOrder === Array()
````
#### results
````javascript
typeof myMock.mock.results === Array()
````
### mockClear
````javascript
() => {
	this._mockState.delete(f);
	return f;
}
````
### mockReset
````javascript
() => {
	f.mockClear();

	this._mockConfigRegistry.delete(f);

	return f;
}
````
### mockRestore
````javascript
() => {
	f.mockReset();
	
	return restore ? restore() : undefined;
}
````
### mockReturnValueOnce
````javascript
value => {
	// next function call will return this value or default 			
	return 	value
	const mockConfig = this._ensureMockConfig(f);

	mockConfig.specificReturnValues.push(value);
	return f;
}
````
### mockResolvedValueOnce
### mockRejectedValueOnce
### mockReturnValue
### mockResolvedValue
### mockRejectedValue
### mockImplementationOnce
### mockImplementation
### mockReturnThis
### mockName
### getMockName
