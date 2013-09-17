# django-simple-search 
## By Mike Hostetler (mike@squarepegsystems.com)

I was looking for a portable, simple way to do search in a Django project. Sure, [Haystack](http://haystacksearch.org/) is nice, but it was overkill for what my need is. I needed something simple.

Googling around I found this blog post by Julien Phalip:

http://julienphalip.com/post/2825034077/adding-search-to-a-django-site-in-a-snap

And it seemed, in theory to work. So I took what he did and put it into a something to simply pop into your Django project and go.

The only thing this app really has is `utils`, which has all of Julien's functions in it. I did generized his view function to be . . . well, generic.

The `generic_search` function may be all need to do. Example:

      ### views.py
      from myblog.models import BlogPost
      from search.utils import generic_search

      def search(request):

        posts = generic_search(request,BlogPost,["title","content"],query_param="search")

        posts.order_by("-pub_date")        

        return render_to_response(.....)

That should be it.

Look at the test cases for more examples.

Things that may or may not happen. Fork if willing to help out.

    * use setuptools
    * use PostgreSQL TSearch 
    * use MySQL FullText Search


