# hanbali-fiqh-xml
# An XML database of religious jurisprudence from Hanbali school resources

## Overview
This XML structure assumes the [ACTION] to be the basic unit of fiqh. Each [ACTION] is a child of either [Conditions], [Invalidators], or the five degrees, eg [Obligatory], [Recommended], etc. Those elements are children of a [CHAMBER] (a sub-section), which is a child of a [GATE] (the traditional 'bab' of fiqh).

Each [ACTION] can have an [Expiation] and an [Exception] children, the later having one or more [ACTION] children. Each [ACTION] and all other elements can have a [Source] child, referencing the [Source_Ref] elements with the [Bibliography] children. Verb phrases are in gerund form.

For viewing and navigating, use

http://countwordsfree.com/xmlviewer

Plan to write similar UI via 

https://www.jstree.com

## Data Structure
ALL CAPS elements are to be uniquely named. Title case elements are set.

	<GATE> (the traditional 'bab' of fiqh books)
		<CHAMBER> (a sub-section within a bab)
			<Description>
				<Descrip>A general description needed for or beyond what follows.</Descrip>
				<Source>Scholar name</Source>
			</Description>
			<Invalidators> (or any other action categories, eg Conditions, Obligatory, Neutral, Forbidden, etc)
				<ACTION>
					<Descrip>Action in gerund form.</Descrip>
					
					<Source>Scholar name</Source>
					
					<Index>Index as float if part of a sequence for entire chamber, eg 1.0, 4.6, 101.0, etc.</Index>
					
					<Expiation>
						<Descrip>Action in gerund form.</Descrip>
						<Source>Scholar name</Source>
					</Expiation>
					
					<Exceptions>
						<ACTION>
							<Descrip>Action in gerund form.</Descrip>
							<Source>Scholar name</Source>
						</ACTION>
					</Exceptions>
				</ACTION>
			</Invalidators>
		</CHAMBER>
	</GATE>

## Ideas
* Add dates and fara'idh and mustahab acts on hijri calendar
* Have javascript website bring up acts per today's date
