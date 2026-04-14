# Mixed Content Fix Specification - pedrofsn.com.br

## Problem Description

The browser console shows the following Mixed Content error:

```
Mixed Content: The page at 'https://pedrofsn.com.br/#' was loaded over HTTPS, 
but requested an insecure stylesheet 'http://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,300italic,400italic'. 
This request has been blocked; the content must be served over HTTPS.
```

This error occurs when an HTTPS page attempts to load resources over HTTP, which is blocked by modern browsers for security reasons.

## Root Cause

In the CSS file `css/style.css`, line 2, the Google Fonts import uses an HTTP URL instead of HTTPS:

```css
@import url('http://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,300italic,400italic');
```

The URL uses `http://` instead of `https://`, causing the Mixed Content blocking issue when the site is served over HTTPS.

## Solution

Change the font import URL from HTTP to HTTPS:

**Before:**
```css
@import url('http://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,300italic,400italic');
```

**After:**
```css
@import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,300italic,400italic');
```

## Files That Need to Be Modified

| File | Line | Change Required |
|------|------|-----------------|
| `css/style.css` | 2 | Change `http://fonts.googleapis.com` to `https://fonts.googleapis.com` |

## Verification Steps

1. **Local Verification:**
   - Open `css/style.css` and confirm the import URL now uses `https://`
   - Verify the change: `grep -n "fonts.googleapis.com" css/style.css`

2. **Browser Verification:**
   - Clear browser cache
   - Visit `https://pedrofsn.com.br`
   - Open Developer Console (F12)
   - Confirm no Mixed Content errors appear
   - Verify the Source Sans Pro font still loads correctly

3. **Production Deployment:**
   - Deploy the updated `css/style.css` to production
   - Test the live site to ensure the font loads properly over HTTPS
