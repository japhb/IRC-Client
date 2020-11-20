[![Build Status](https://travis-ci.org/perl6-community-modules/perl6-IRC-Client.svg)](https://travis-ci.org/raku-community-modules/IRC-Client)

# NAME

IRC::Client - Extendable Internet Relay Chat client

# SYNOPSIS

```raku
    use IRC::Client;
    use Pastebin::Shadowcat;

    .run with IRC::Client.new:
        :host<irc.freenode.net>
        :channels<#rakubot #zofbot>
        :debug
        :plugins(
            class { method irc-to-me ($ where /hello/) { 'Hello to you too!'} }
        )
        :filters(
            -> $text where .chars > 200 {
                'The output is too large to show here. See: '
                ~ Pastebin::Shadowcat.new.paste: $text;
            }
        );
```

# DESCRIPTION

The module provides the means to create clients to communicate with
IRC (Internet Relay Chat) servers. Has support for non-blocking responses
and output post-processing.

# DOCUMENTATION MAP

* [Blog Post](http://perl6.party/post/IRC-Client-Perl-6-Multi-Server-IRC-Module)
* [Basics Tutorial](docs/01-basics.md)
* [Event Reference](docs/02-event-reference.md)
* [Method Reference](docs/03-method-reference.md)
* [Big-Picture Behaviour](docs/04-big-picture-behaviour.md)
* [Examples](examples/)

---

#### REPOSITORY

Fork this module on GitHub:
https://github.com/raku-community-modules/IRC-Client

#### BUGS

To report bugs or request features, please use
https://github.com/raku-community-modules/IRC-Client/issues

#### AUTHOR

Zoffix Znet (http://zoffix.com/)

#### CONTRIBUTORS

[tyil](https://www.tyil.nl/)
[MasterDuke17](https://github.com/raku-community-modules/IRC-Client/commits?author=MasterDuke17)

#### LICENSE

You can use and distribute this module under the terms of the
The Artistic License 2.0. See the `LICENSE` file included in this
distribution for complete details.

The `META6.json` file of this distribution may be distributed and modified
without restrictions or attribution.
