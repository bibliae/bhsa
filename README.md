# BHSA

## Biblia Hebraica Stuttgartensia (Amstelodamensis)
![text-fabric](https://raw.github.com/ETCBC/text-fabric/master/docs/tf.png)

This is the
[text-fabric](https://github.com/ETCBC/text-fabric/wiki)
version of the Hebrew Bible Database,
containing the text of the Hebrew Bible augmented with linguistic annotations compiled by the
[Eep Talstra Centre for Bible and Computer](http://www.godgeleerdheid.vu.nl/en/research/institutes-and-centres/eep-talstra-centre-for-bible-and-computer/index.aspx), VU University Amsterdam.

The text is based on the
[Bibila Hebraica Stuttgartensia](https://www.academic-bible.com/en/online-bibles/biblia-hebraica-stuttgartensia-bhs/read-the-bible-text/)
edited by Karl Elliger and Wilhelm Rudolph,
Fifth Revised Edition, edited by Adrian Schenker,
© 1977 and 1997 Deutsche Bibelgesellschaft, Stuttgart.

The [text-fabric](https://github.com/ETCBC/text-fabric/wiki) version has been prepared
by Dirk Roorda [Data Archiving and Networked Services](https://dans.knaw.nl/en/front-page?set_language=en),
with thanks to
Martijn Naaijer,
[Cody Kingham](http://www.codykingham.com)
and Constantijn Sikkel.

This dataset contains version **4b** which shows up in
[SHEBANQ](https://shebanq.ancient-data.org/sources).

We allso intend to add version **4** of shebanq, a new moving version **c**, and new fixed
versions **2017**, **2019** etc.

## Provenance
* The source data resides on a server of the ETCBC, managed by Constantijn Sikkel.
  He has made that data available as an [MQL](https://emdros.org/mql.html) database dump, `bhs4.mql`.
* `bhs4.mql` has been enriched with statistical features and a phonetic transcriptions
  by Dirk Roorda, using
  [LAF-Fabric](https://github.com/ETCBC/laf-fabric) (precursor of text-fabric).
  The enriched version has been exported to MQL again, as `x_etcbc4b.mql`, for use in SHEBANQ.
  `x_etcbc4b.mql` has been archived in the DANS repository [Easy](https://doi.org/10.17026/dans-z6y-skyh).
* `x_etcbc4b.mql` has been downloaded from Easy, and transformed into a text-fabric data set, in this repository.
  The mql source, the program, and the result are all in this repo.

## Workflow
The pipeline above is complicated and not free of
[cruft](https://en.wikipedia.org/wiki/Cruft).
That's why a simplification of it is in the works.
The new pipeline will work like this:

The ETCBC:

* exports a full MQL version of the Hebrew Text database: `bhsa.mql`;
* converts it to a text-fabric resource: `bhsa/core`;
* enriches it with additional text-fabric data modules
  * `bhsa/stats`: statistical features,
  * `bhsa/phono`: phonetic transcription,
  * `bhsa/parallel`: parallel passages,
  * `bhsa/valence`: verbal valence
* commits the text-fabric data changes to this github repository;
* updates the website [shebanq](https://shebanq.ancient-data.org):
  * exports all text-fabric data (core plus modules) to mql: `x_bhsa.mql`;
  * compiles the text-fabric data into website friendly mysql databases;
  * compiles annotation sets from the text-fabric data modules `parallels` and `valence`;
  * transfers the new mql, mysql and annotations to SHEBANQ, with the result that
    * shebanq queries are executed against the data in `x_bhsa.mql`;
    * shebanq text and data display is based on the mysql databases based on the same `x_bhsa.mql`;
    * annotations show up correctly alongside the text.
  
Once this pipeline is fully operational, it will be executed weekly.
In SHEBANQ the weekly results will land in a continuous version called `c` (not yet in shebanq).

## Reproducible science
We intend to follow a practice that allows for data updates on the one hand, and reproduction of old
results on the other.

Besides the continously changing version `c`, there will be fixed versions.
It will not be possible to publish queries and annotations executed agains the `c` version, but they can be shared.
It is likely that they will break, when version `c` is modified, week after week.
So, saved queries against this version are not guaranteed to show their original results.

For reliable query saving, every two years a new fixed version, called `2017`, `2019`, ... will be added.

Fixed versions in SHEBANQ will remain there forever, and publishing queries and annotations against fixed
versions will remain supported.

In particular, versions `4` and `4b` are here to stay, since they have published queries based on them.
These versions are also firmly entrenched in the academic record, by virtue of being archived:

* [4, archived, DOI: /doi.org/10.17026/dans-2z3-arxf](https://doi.org/10.17026/dans-2z3-arxf)
* [4b, archived, DOI: doi.org/10.17026/dans-z6y-skyh](https://doi.org/10.17026/dans-z6y-skyh)

We intend to archive future fixed versions by snapshotting this repo into Zenodo, like has been done
with a provisional version `4c`:

* [4c, snapshotted to Zenodo, DOI: doi.org/10.5281/zenodo.591507](https://doi.org/10.5281/zenodo.591507)

## License

This work is licensed under a
[Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/).
That means:

* You may download the data and use it: process, copy, modify;
* You may use the data to create new software applications;
* You may use the data for research and publish any amount of results;
* When you publish this data or results you obtained from them, you have to comply with the following:
  * give proper attribution to the data when you use it in new applications,
    by citing this persistent identifier:
    [10.17026/dans-z6y-skyh](http://dx.doi.org/10.17026%2Fdans-z6y-skyh).
  * do not use the data for commercial applications without consent;
    for any commercial use, please contact the
    [German Bible Society](zentrale@dbg.de).

# How to use

This data can be processed by 
[Text-Fabric](https://github.com/ETCBC/text-fabric/wiki).

See also 
[tutorial (Hebrew)](https://github.com/etcbc/text-fabric/blob/master/docs/tutorial.ipynb)
and
[tutorial (search)](https://github.com/etcbc/text-fabric/blob/master/docs/searchTutorial.ipynb).
