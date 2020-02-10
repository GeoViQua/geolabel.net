---
layout: page
title: API
---

**Current cloud deployments**

- [`https://glbservice-nvrpuhxwyq-ew.a.run.app/glbservice/api/v1`](https://glbservice-nvrpuhxwyq-ew.a.run.app/glbservice/api/v1)
- [`https://6x843uryh9.execute-api.eu-central-1.amazonaws.com/glbservice/api/v1`](https://6x843uryh9.execute-api.eu-central-1.amazonaws.com/glbservice/api/v1) (partial implementation only)

------

# REST API v1 Resources

Some [implementations](/implementations) provide more features, e.g. PNG rendering.

## SVG

Operations to retrieve GEO label SVG representations.

### `GET /api/v1/geolabel`

#### Query parameters

<table class="table">
	<thead>
		<tr>
			<th>Name</th>
			<th>Required</th>
			<th>Data Type</th>
			<th>Description</th>
		</tr>
		<tr>
			<th>metadata*</th>
			<td>optional</td>
			<td>URL</td>
			<td>Encoded URL of producer metadata document. Metadata document must be ISO19115, ISO19157, FGDC or GVQ-PQM compliant.</td>
		</tr>
		<tr>
			<th>feedback*</th>
			<td>optional</td>
			<td>URL</td>
			<td>Encoded URL of feedback document. Feedback document must be GVQ-UQM compliant.</td>
		</tr>
		<tr>
			<th>parent_metadata</th>
			<td>optional</td>
			<td>URL</td>
			<td>Encoded URL of parent dataset's producer metadata document. Metadata document must be ISO19115, ISO19157, FGDC or GVQ-PQM compliant.</td>
		</tr>
		<tr>
			<th>parent_feedback</th>
			<td>optional</td>
			<td>URL</td>
			<td>Encoded URL of parent dataset's feedback document. Feedback document must be GVQ-UQM compliant.</td>
		</tr>
		<tr>
			<th>size</th>
			<td>optional</td>
			<td>int</td>
			<td>Required size of the GEO label SVG in pixels. If not specified, the default size is 200x200 pixels.</td>
		</tr>
	</thead>
</table>

<b>*</b> At least one of these parameters must be provided.

### `POST /api/v1/geolabel`

<table class="table">
	<thead>
		<tr>
			<th>Name</th>
			<th>Required</th>
			<th>Data Type</th>
			<th>Description</th>
		</tr>
		<tr>
			<th>metadata*</th>
			<td>optional</td>
			<td>File</td>
			<td>Producer XML metadata document. Metadata document must be ISO19115, ISO19157, FGDC or GVQ-PQM compliant.</td>
		</tr>
		<tr>
			<th>feedback*</th>
			<td>optional</td>
			<td>File</td>
			<td>Feedback XML document. Feedback document must be GVQ-UQM compliant.</td>
		</tr>
		<tr>
			<th>parent_metadata</th>
			<td>optional</td>
			<td>File</td>
			<td>Parent dataset's producer XML metadata document. Metadata document must be ISO19115, ISO19157, FGDC or GVQ-PQM compliant.</td>
		</tr>
		<tr>
			<th>parent_feedback</th>
			<td>optional</td>
			<td>File</td>
			<td>Parent dataset's feedback XML document. Feedback document must be GVQ-UQM compliant.</td>
		</tr>
		<tr>
			<th>size</th>
			<td>optional</td>
			<td>int</td>
			<td>Required size of the GEO label SVG in pixels. If not specified, the default size is 200x200 pixels.</td>
		</tr>
	</thead>
</table>

<b>*</b> Although optional, at least one of these parameters must be provided.

## Facets

Operations to retrieve GEO label JSON representations.

### `GET /api/v1/facets`

<table class="table">
	<thead>
		<tr>
			<th>Name</th>
			<th>Required</th>
			<th>Data Type</th>
			<th>Description</th>
		</tr>
		<tr>
			<th>metadata*</th>
			<td>optional</td>
			<td>URL</td>
			<td>Encoded URL of producer metadata document. Metadata document must be ISO19115, ISO19157, FGDC or GVQ-PQM compliant.</td>
		</tr>
		<tr>
			<th>feedback*</th>
			<td>optional</td>
			<td>URL</td>
			<td>Encoded URL of feedback document. Feedback document must be GVQ-UQM compliant.</td>
		</tr>
	</thead>
</table>

<b>*</b> At least one of these parameters must be provided.

### `POST /api/v1/facets`

<table class="table">
	<thead>
		<tr>
			<th>Name</th>
			<th>Required</th>
			<th>Data Type</th>
			<th>Description</th>
		</tr>
		<tr>
			<th>metadata*</th>
			<td>optional</td>
			<td>File</td>
			<td>Producer XML metadata document. Metadata document must be ISO19115, ISO19157, FGDC or GVQ-PQM compliant.</td>
		</tr>
		<tr>
			<th>feedback*</th>
			<td>optional</td>
			<td>File</td>
			<td>Feedback XML document. Feedback document must be GVQ-UQM compliant.</td>
		</tr>
	</thead>
</table>

<b>*</b> At least one of these parameters must be provided.

## Drilldown

Operations to retrieve styled representations of metadata records, providing details on specific facets.

### `GET /api/v1/drilldown`

<table class="table">
	<thead>
		<tr>
			<th>Name</th>
			<th>Required</th>
			<th>Data Type</th>
			<th>Description</th>
		</tr>
		<tr>
			<th>metadata</th>
			<td>optional</td>
			<td>URL</td>
			<td>URL to producer metadata document. Metadata document must be ISO19115, ISO19157, FGDC or GVQ-PQM compliant.</td>
		</tr>
		<tr>
			<th>feedback</th>
			<td>optional</td>
			<td>URL</td>
			<td>URL to feedback document. Feedback document must be GVQ-UQM compliant.</td>
		</tr>
		<tr>
			<th>facet</th>
			<td>required</td>
			<td>string</td>
			<td>GEO label facet identifier. Allowed values:
			<ul>
				<li>producer_profile</li>
				<li>producer_comments</li>
				<li>lineage_information</li>
				<li>standards_complaince</li>
				<li>quality_information</li>
				<li>user_feedback</li>
				<li>expert_review</li>
				<li>citations_information</li>
			</ul>
			</td>
		</tr>
	</thead>
</table>
