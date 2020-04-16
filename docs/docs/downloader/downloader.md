---
title: Downloader
date: 20200410
author: Lyz
---

Python program to obtain the metadata and content from the sites populating the
database.

The idea is to have a centralized scheduler that triggers celery jobs to be
consumed by worker processes. We'd have different worker processes for
each data source, so it should be easy to support new sites.

# Requirements

* It must download the metadata and content to the [database|filesystem].
* All the user information must remain local.
* It must preserve the anonymity of the user as much as possible.
* It must store all the metadata needed by the other programs in the database.

# Extractors

An extractor is an object that transforms the source data into the SQLAlchemy
objects defined in the [models]() schema.
