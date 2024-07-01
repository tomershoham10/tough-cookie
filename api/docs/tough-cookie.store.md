<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [tough-cookie](./tough-cookie.md) &gt; [Store](./tough-cookie.store.md)

## Store class

Base class for [CookieJar](./tough-cookie.cookiejar.md) stores.

The storage model for each [CookieJar](./tough-cookie.cookiejar.md) instance can be replaced with a custom implementation. The default is [MemoryCookieStore](./tough-cookie.memorycookiestore.md)<!-- -->.

**Signature:**

```typescript
export declare class Store 
```

## Remarks

- Stores should inherit from the base Store class, which is available as a top-level export.

- Stores are asynchronous by default, but if [Store.synchronous](./tough-cookie.store.synchronous.md) is set to true, then the `*Sync` methods of the containing [CookieJar](./tough-cookie.cookiejar.md) can be used.

## Constructors

<table><thead><tr><th>

Constructor


</th><th>

Modifiers


</th><th>

Description


</th></tr></thead>
<tbody><tr><td>

[(constructor)()](./tough-cookie.store._constructor_.md)


</td><td>


</td><td>

Constructs a new instance of the `Store` class


</td></tr>
</tbody></table>

## Properties

<table><thead><tr><th>

Property


</th><th>

Modifiers


</th><th>

Type


</th><th>

Description


</th></tr></thead>
<tbody><tr><td>

[synchronous](./tough-cookie.store.synchronous.md)


</td><td>


</td><td>

boolean


</td><td>

Store implementations that support synchronous methods must return `true`<!-- -->.


</td></tr>
</tbody></table>

## Methods

<table><thead><tr><th>

Method


</th><th>

Modifiers


</th><th>

Description


</th></tr></thead>
<tbody><tr><td>

[findCookie(domain, path, key)](./tough-cookie.store.findcookie.md)


</td><td>


</td><td>

Retrieve a [Cookie](./tough-cookie.cookie.md) with the given `domain`<!-- -->, `path`<!-- -->, and `key` (`name`<!-- -->). The RFC maintains that exactly one of these cookies should exist in a store. If the store is using versioning, this means that the latest or newest such cookie should be returned.

Callback takes an error and the resulting Cookie object. If no cookie is found then null MUST be passed instead (that is, not an error).


</td></tr>
<tr><td>

[findCookie(domain, path, key, callback)](./tough-cookie.store.findcookie_1.md)


</td><td>


</td><td>

Retrieve a [Cookie](./tough-cookie.cookie.md) with the given `domain`<!-- -->, `path`<!-- -->, and `key` (`name`<!-- -->). The RFC maintains that exactly one of these cookies should exist in a store. If the store is using versioning, this means that the latest or newest such cookie should be returned.

Callback takes an error and the resulting Cookie object. If no cookie is found then null MUST be passed instead (that is, not an error).


</td></tr>
<tr><td>

[findCookies(domain, path, allowSpecialUseDomain)](./tough-cookie.store.findcookies.md)


</td><td>


</td><td>

Locates all [Cookie](./tough-cookie.cookie.md) values matching the given `domain` and `path`<!-- -->.

The resulting list is checked for applicability to the current request according to the RFC (`domain-match`<!-- -->, `path-match`<!-- -->, `http-only-flag`<!-- -->, `secure-flag`<!-- -->, `expiry`<!-- -->, and so on), so it's OK to use an optimistic search algorithm when implementing this method. However, the search algorithm used SHOULD try to find cookies that [domainMatch()](./tough-cookie.domainmatch.md) the `domain` and [pathMatch()](./tough-cookie.pathmatch.md) the `path` in order to limit the amount of checking that needs to be done.


</td></tr>
<tr><td>

[findCookies(domain, path, allowSpecialUseDomain, callback)](./tough-cookie.store.findcookies_1.md)


</td><td>


</td><td>

Locates all [Cookie](./tough-cookie.cookie.md) values matching the given `domain` and `path`<!-- -->.

The resulting list is checked for applicability to the current request according to the RFC (`domain-match`<!-- -->, `path-match`<!-- -->, `http-only-flag`<!-- -->, `secure-flag`<!-- -->, `expiry`<!-- -->, and so on), so it's OK to use an optimistic search algorithm when implementing this method. However, the search algorithm used SHOULD try to find cookies that [domainMatch()](./tough-cookie.domainmatch.md) the `domain` and [pathMatch()](./tough-cookie.pathmatch.md) the `path` in order to limit the amount of checking that needs to be done.


</td></tr>
<tr><td>

[getAllCookies()](./tough-cookie.store.getallcookies.md)


</td><td>


</td><td>

Gets all the cookies in the store.


</td></tr>
<tr><td>

[getAllCookies(callback)](./tough-cookie.store.getallcookies_1.md)


</td><td>


</td><td>

Gets all the cookies in the store.


</td></tr>
<tr><td>

[putCookie(cookie)](./tough-cookie.store.putcookie.md)


</td><td>


</td><td>

Adds a new [Cookie](./tough-cookie.cookie.md) to the store. The implementation SHOULD replace any existing cookie with the same `domain`<!-- -->, `path`<!-- -->, and `key` properties.


</td></tr>
<tr><td>

[putCookie(cookie, callback)](./tough-cookie.store.putcookie_1.md)


</td><td>


</td><td>

Adds a new [Cookie](./tough-cookie.cookie.md) to the store. The implementation SHOULD replace any existing cookie with the same `domain`<!-- -->, `path`<!-- -->, and `key` properties.


</td></tr>
<tr><td>

[removeAllCookies()](./tough-cookie.store.removeallcookies.md)


</td><td>


</td><td>

Removes all cookies from the store.


</td></tr>
<tr><td>

[removeAllCookies(callback)](./tough-cookie.store.removeallcookies_1.md)


</td><td>


</td><td>

Removes all cookies from the store.


</td></tr>
<tr><td>

[removeCookie(domain, path, key)](./tough-cookie.store.removecookie.md)


</td><td>


</td><td>

Remove a cookie from the store (see notes on `findCookie` about the uniqueness constraint).


</td></tr>
<tr><td>

[removeCookie(domain, path, key, callback)](./tough-cookie.store.removecookie_1.md)


</td><td>


</td><td>

Remove a cookie from the store (see notes on `findCookie` about the uniqueness constraint).


</td></tr>
<tr><td>

[removeCookies(domain, path)](./tough-cookie.store.removecookies.md)


</td><td>


</td><td>

Removes matching cookies from the store. The `path` parameter is optional and if missing, means all paths in a domain should be removed.


</td></tr>
<tr><td>

[removeCookies(domain, path, callback)](./tough-cookie.store.removecookies_1.md)


</td><td>


</td><td>

Removes matching cookies from the store. The `path` parameter is optional and if missing, means all paths in a domain should be removed.


</td></tr>
<tr><td>

[updateCookie(oldCookie, newCookie)](./tough-cookie.store.updatecookie.md)


</td><td>


</td><td>

Update an existing [Cookie](./tough-cookie.cookie.md)<!-- -->. The implementation MUST update the `value` for a cookie with the same `domain`<!-- -->, `path`<!-- -->, and `key`<!-- -->. The implementation SHOULD check that the old value in the store is equivalent to oldCookie - how the conflict is resolved is up to the store.


</td></tr>
<tr><td>

[updateCookie(oldCookie, newCookie, callback)](./tough-cookie.store.updatecookie_1.md)


</td><td>


</td><td>

Update an existing [Cookie](./tough-cookie.cookie.md)<!-- -->. The implementation MUST update the `value` for a cookie with the same `domain`<!-- -->, `path`<!-- -->, and `key`<!-- -->. The implementation SHOULD check that the old value in the store is equivalent to oldCookie - how the conflict is resolved is up to the store.


</td></tr>
</tbody></table>