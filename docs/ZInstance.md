---
layout: default
title: ZInstance
has_children: true
nav_order: 2
---

### Description
A sandboxed version of [Instance](https://create.roblox.com/docs/reference/engine/classes/Instance).

#### Properties

| Type | Key | Default Value |  
| --- | --- | --- |  
| string | ClassName | ZInstance |  
| string | [Name](#name) | `ClassName#counter ` |
| table | [ClassList](#classlist) | {*userdata*} |

### Methods

| Return Type | Name |
| --- | --- |
| ZInstance | [Get](#get) (name: *string*) |
| table | [List](#list) (pattern: *string?*, search: *boolean?*) |
| void | [DestroyList](#destroylist) (pattern: *string?*, search: *boolean?*) |

---

### Property Descriptions

<a name="name"></a>
`string` **Name** *= ClassName#counter*
- By default, every new instance will be named by it's `ClassName` followed by it's index counter.
- **ZInstance** keeps track of all instances it creates and continuously increment a counter.

---

<a name="classlist"></a>
`table` **ClassList** *= {userdata}*
- This table is a dictionary of classes that are available in this ZSharp environment.
- These classes are not usable and just are proxies of actual classes.

---

### Method Descriptions

<a name="get"></a>
`ZInstance` **Get**(name: *string*)
- Gets a ZInstance by name. If there are multiple instances with the same name, it will only return the first one found.
- The return value can differ base on the instance's class, if the instance stored is a [ZSound](ZSound), it will return a ZSound.

---

<a name="list"></a>
`table` **List**(pattern: *string?*, search: *boolean?*)
- Returns a list of instances.
- `pattern ~= nil`
	- Then it will return every available instance.
- `pattern ~= nil and search ~= true` 
	- Then it will search for instances with names exactly matches the `pattern`.
- `pattern ~= nil and search == true`
	- Then it will `string.match` instances with names matching the pattern.

---

<a name="destroylist"></a>
`void` **DestroyList**(pattern: *string?*, search: *boolean?*)
- `pattern` & `search` works the same as [List](#list)
- It will destroy every matching item.