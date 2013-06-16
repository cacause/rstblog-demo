rstblog-demo
============

CaCause is a plugin for managing blog comments. Unlike comment systems
like Disqus which carry comments from a third-party platform to the client browser,
CaCause make comments part of the static blog. We feel this approach is in line
with strong ideas standing behind static blogs:

*    own your data, don't delegate to a 3rd-party, 
*    keep capability to rebuild the entire blog offline.

**How it works**

Main idea is that approved comments exist on disk in Markup format and 
CaCause pluging is called during blog build to embed article pages with related
comments. You probably think "that sounds great! But how are created the
comments? How is managed the approval process?". Well, that's another chapter 
of the CaCause story which is still under development. But the CaCause plugin 
is the first piece to achieve our goal. 

**Plugin usage**

A sub-directory is dedicated to store comments. Each comment is a file in REST 
format (.rst file extension). The header is used to define
comment metadata: author name, author email, published date.

Customize blog configuration defined in *config.yml*

    # register cacause plugin
    active_modules: [blog, tags, cacause]

    # configure cacause
    cacause_dir: comments
    cacause_gravatar: True

Parameters: 

*   *cacause_dir* is a directory under RstBlog root directory where comments are
stored in REST format.
*   *cacause_gravatar* is a boolean to enable or disable Gravatar support.

**Example**

Have a look to this tiny RstBlog demo.
