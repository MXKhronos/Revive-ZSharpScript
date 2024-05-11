---
layout: default
title: EventService
parent: Class
nav_order: 5
---

### Description
EventService is a ZSharp unique library for handling game events. From `OnClockTick` to `WeatherService.OnWeatherSet`, see [event key list](#eventkeys) for a list of event keys that exists.

### Properties

| Type | Key | Default Value |  
| --- | --- | --- |
| No available properties |

### Methods

| Return Type | Name |
| --- | --- |
| [EventPacket](#eventpacket) | [Invoke](#invoke) (key: *string*, ...) |
| () -> nil | [OnInvoked](#oninvoked) (key: *string*, func: *(event: EventPacket, ...any) -> nil*, position: *number?*) |
| {[number]: string} | [ListHandlers](#listhandlers) (pattern: *string?*, search: *boolean?*)

### Property Descriptions
No available properties

---
### Method Descriptions

<a name="invoke"></a>
[`EventPacket`](#eventpacket) **Invoke**(key: *string*, ...)
- Invokes an event of `key`. To see list of active event handlers, use [`EventService:ListHandlers()`](#listhandlers).

---

<a name="oninvoked"></a>
`() -> nil` **OnInvoked**(key: *string*, func: *(event: [EventPacket](#eventpacket), ...any) -> nil*, position: *number?*)
- Connects a `function` to handle when a event of `key` is invoked.
- Returns a `function`, which disconnects the handler when called.

---

<a name="listhandlers"></a>
`{[number]: string}` **ListHandlers**(pattern: *string?*, search: *boolean?*)
- Returns a sorted list of event handler keys.
- `pattern ~= nil`
	- Then it will return every available instance.
- `pattern ~= nil and search ~= true` 
	- Then it will search for instances with names exactly matches the `pattern`.
- `pattern ~= nil and search == true`
	- Then it will `string.match` instances with names matching the pattern.

---
<br>

## Event Packet
<a name="eventpacket"></a>

### Description
Event packets are objects that allow you to cancel events.

### Properties

| Type | Key | Default Value |  
| --- | --- | --- |
| boolean | [Cancelled](#cancelled) | false |
| boolean | [Completed](#completed) | false |
| {[number]: Player}? | Players | nil |
<br>

### Methods

| Return Type | Name |
| --- | --- |
| nil | [SetCancelled](#setcancelled) (value: *boolean*) |

---
<br>

### Property Descriptions

<a name="cancelled"></a>
`boolean` **Cancelled** *= false*
- Status of the event, when cancelled, every other proceeding event handlers will not be invoked.
- Use [`EventPacket:SetCancelled(...)`](#setcancelled) to set this value.

<a name="completed"></a>
`boolean` **Completed** *= false*
- When completed, canceling events will have no effect.

---
<br>

### Method Descriptions

<a name="setcancelled"></a>
`nil` **SetCancelled**(value: *boolean*)
- Cancels an event. E.g. If `WeatherService.OnWeatherSet` is cancelled, the weather will not be set by `WeatherService`.

---
<br>

## Event Key List
<a name="eventkeys"></a>

| Keys |
| --- |
| `OnClockTick` |
| `WeatherService.OnWeatherSet` |

---