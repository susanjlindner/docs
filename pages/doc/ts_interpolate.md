---
title: interpolate Function
keywords: query language reference
tags: [reference page]
sidebar: doc_sidebar
permalink: ts_interpolate.html
summary: Reference to the interpolate() function
---
## Summary
```
interpolate(<expression>)
```
Fills in gaps in `expression` with a continuous linear interpolation of points.


## Parameters

<table>
<tbody>
<thead>
<tr><th width="20%">Parameter</th><th width="80%">Description</th></tr>
</thead>
<tr>
<td markdown="span"> [expression](query_language_reference.html#expressions)</td>
<td>Expression in which you want to replace gaps in data with the next value. </td>
</tr>
</tbody>
</table>

## Description

The `interpolate()` function replaces a gap of missing data (dashed line) with a solid line. The value assigned to the new solid line depends on where the interpolation occurred in relation to the value on the y-axis.

For example, suppose there is a gap of missing data in between two reported point values of 2 and 1. The value assigned to that gap of missing data will be between 2 and 1, with the displayed value dependent on where it intersects the y-axis. When Wavefront performs interpolation, it applies `interpolate()` to the first 85% of a chart window.

## Examples

The following example zooms in on an area of a chart where data are missing. Wavefront uses dashed lines to indicate the missing data.

![interpolate before](images/interpolate_before.png)

When you use `interpolate()` for this use case, the dashed lines are replaced with filled lines, indistinguishable from areas where data are available.

![interpolate after](images/interpolate_after.png)


## See Also

[Using Moving and Tumbling Time Windows to Highlight trends](query_language_windows_trends.html)

Other missing data functions include [default](ts_default.html), [next](ts_next.html), and [last](ts_last.html).
