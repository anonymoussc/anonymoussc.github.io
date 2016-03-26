---
title:  "API response pagination"
date:   2016-03-24 08:05:00
summary: Splitting up data into multiple HTTP requests, for limiting HTTP Response size.
---

### Pagination, what for ?
Splitting up data into multiple HTTP requests, for limiting HTTP Response size.

### The reason ?

1. Downloading more takes longer.
2. Trying to return big data of 1000,000 into infinity records in one go might takes longer into eternity.
3. "Presentation logic iterating over 1000,000 into infinity records is fun" - Nobody, ever.

### Example 1 using cursor with fractal

{% highlight PHP %}
use Acme\Model\Book;
use Acme\Transformer\BookTransformer;
use League\Fractal\Pagination\Cursor;
use League\Fractal\Resource\Collection;

$currentCursor  = Input::get('cursor', null);
$previousCursor = Input::get('previous', null);
$limit          = Input::get('limit', 10);

if ($currentCursor) {
    $books = Book::where('id', '>', $currentCursor)->take($limit)->get();
} else {
    $books = Book::take($limit)->get();
}

$newCursor = $books->last()->id;
$cursor = new Cursor($currentCursor, $previousCursor, $newCursor, $books->count());

$resource = new Collection($books, new BookTransformer);
$resource->setCursor($cursor);
{% endhighlight %}

### Example 2 using dingo API

{% highlight PHP %}
class UserController extends BaseController
{
    public function index()
    {
        $users = User::paginate(25);

        return $this->response->paginator($users, new UserTransformer);
    }
}
{% endhighlight %}

Reference :

1. [Pagination - Fractal](http://fractal.thephpleague.com/pagination/)