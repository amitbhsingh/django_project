# Web development : Building a blog app
#### The framework.
> 1 django-admin startproject name
> 2 python

> Creating database  $python manage.py migrate
> Creating user for admin page $python manage.py createsuperuser
> sqllite database for development and postgres database for production
> Migrating database
> object relational mappers are convienient
> $python manage.py sqlmigrate blog 0001
> $ python manage.py migrate
### Quering databases
$ python manage.py shell
rom blog.models import Post

 In [2]: from django.contrib.auth.models import User

In [3]: User.objects.all
Out[3]: <bound method BaseManager.all of <django.contrib.auth.models.UserManager object at 0x1060a15c0>>

In [4]: User.objects.all()
Out[4]: <QuerySet [<User: amitbhsingh>]>
In [5]: User.objects.first()
Out[5]: <User: amitbhsingh>
In [14]: Post.objects.all()
Out[14]: <QuerySet [<Post: Post object (1)>]>

In [15]: exit()
amitkumars-MacBook-Air:django_project amit$ python manage.py shell
Python 3.6.8 |Anaconda custom (64-bit)| (default, Dec 29 2018, 19:04:46)
Type 'copyright', 'credits' or 'license' for more information
IPython 6.5.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: from blog.models import Post

In [2]: from django.contrib.auth.models import User

In [3]: Post.objects.all()
Out[3]: <QuerySet [<Post: Blog1>]>

In [4]: user=User.objects.filter(username='amitbhsingh').first()

In [5]: user
Out[5]: <User: amitbhsingh>

In [6]: post_2=Post(title='Blog 2', content='Second post content',autho
   ...: r_id=user.id)
In [7]: post_2.save()
In [9]: Post.objects.all()
Out[9]: <QuerySet [<Post: Blog1>, <Post: Blog 2>]>
post.date_posted
Out[14]: datetime.datetime(2019, 8, 13, 22, 16, 4, 332233, tzinfo=<UTC>
  user.post_set
Out[19]: <django.db.models.fields.related_descriptors.create_reverse_many_to_one_manager.<locals>.RelatedManager at 0x1116e1cc0>

In [20]: user.post_set.all()
Out[20]: <QuerySet [<Post: Blog1>, <Post: Blog 2>]>

In [21]: user.post_set.create(title='Blog 3',content='Third post conten
    ...: t')
Out[21]: <Post: Blog 3>


# Video 10 Create delete and update all in one

# Video 12:
** Seding email to users for resetting the passwordss
https://www.youtube.com/redirect?q=https%3A%2F%2Fdocs.djangoproject.com%2Fen%2F2.1%2Ftopics%2Femail%2F%23configuring-email-for-development&v=-tyBEsHSv7w&redir_token=H4aNuMVgYk_iKnRJHmANyHXHxAB8MTU2NjQ0Njg0M0AxNTY2MzYwNDQz&event=video_description


#### Adding the secret key via terminla
> vim .bash_profile

# Video 13 Deploying the application
* How to deploy to your own linux server
* How to deploy to heroku

## Video 17 Deploying on heroku
* heroku run python manage.py migrate #
* heroku run bash # opens the heroku bash linux command
# heroku Delploying app on heroku
* 1 heroku create appname
* Creating a database
* creating superuser
* 2 heroku run bash => to run the heroku bash
* heroku machines are called dynos and they are linux based so we need to run linux commands
