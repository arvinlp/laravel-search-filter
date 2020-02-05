# laravel-search-filter

<a href="https://arvinlp.github.io/laravel-search-filter/" title="Laravel Search Filter">Laravel Search Filter page on GitHub</a>

<h2>How Use ?</h2>
<p>in your controller instead of use routine method like :</p>
<pre>
$flight = App\Flight::pageination();
//Or
$flight = App\Flight::with('captain')->pageination();
//Or
$flight = App\Flight::where('active', 1)->pageination();
//Or
$flight = App\Flight::with('captain')->where('active', 1)->all();
//Or
$flight = App\Flight::with('captain')->where('active', 1)->get();
//Or
$flight = App\Flight::with('captain')->where('active', 1)->pageination();
</pre>
<p>
With this class you can parsing get url and using one line code for fetching data with Eloquent and filtered data.
</p>
<pre>
$flight = App\SearchFilter::apply( $request, new Flight, 'all', 'captain' );
</pre>

<h2>Function Arguments</h2>
<h3>SearchFilter::apply( Request, Model, Query Type, Relationships )</h3>
<p>
  <strong>Request(Required) : </strong>
  Illuminate\Http\Request $request;
  Any request laravel can supported like Get, Post, Put, etc.
  But for using search and filters using Get method !
</p>
<p>
  <strong>Model(Required) : </strong>
  Illuminate\Database\Eloquent\Model;
  model should be extened of Eloquent Model. and just passing to function not more!
</p>
<p>
  <strong>Query Type : </strong>
  is String method or can be NULL.
  <ol>
    <li> <b>all</b> : Get All Data</li>
    <li> <b>get</b> : Get Data</li>
    <li> <b>pageination</b> : Get Data With Pageination</li>
  </ol>
  When Query Type is Null or not selected by Default is 'pageination'.
</p>
<p>
  <strong>Relationships : </strong>
  When you need use Eloquent Relation in your query can send by this arg.
  this arg like Main scopeWith can parsing array.
  <pre>
    $relation = 'role';
    //or
    $relation = ['role','access'];
  </pre>
</p>
<hr>
<h4>Thank you</h4>
<h5>Arvin Loripour</h5>
