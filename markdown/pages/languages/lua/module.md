# a module implemetation for lua

add a namespace for lua

## for example : 

### you can write something in file `dirpath/json.lua`


	function encode(...)
	end

	function decode(...)
	end

### and we use as following	

	json = import("dirpath/json.lua")
	json.encode(...)
	json.decode(...)

## here is the code:

	function import(path)
		local func, err = assert(loadfile(path))
		local m = {}
		setmetatable(m, {__index = _G})
		setfenv(func, m)()
		return m
	end

