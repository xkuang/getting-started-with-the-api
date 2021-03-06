# Getting started in perl

1. If you have not already done so, follow the Google Genomics
[sign up instructions](https://cloud.google.com/genomics/downloading-credentials-for-api-access)
to generate and download a valid ``client_secrets.json`` file.  

2. Copy the client_secrets.json file into this directory.

3. Install the perl dependencies and run the code:

    ```
    cpanm Path::Class
    cpanm Net::OAuth2::Client
    cpanm Mozilla::CA
    cpanm LWP::Protocol::https
    perl main.pl
    ```

# Troubleshooting

If you see the error:
```
Can't locate object method "host_port" via package "URI::_generic" at /Library/Perl/5.16/Net/OAuth2/Profile.pm line 197.
```

it's because the access token in `credentials.dat` has expired, and this error
shows up when `Net::OAuth2` tries to refresh it. I don't know how to fix this issue -
so if you do, a pull request (or explanatory issue) would be very welcome!

In the meantime, you can just manually remove the `credentials.dat` file
and everything will work again:
```
cd getting-started-with-the-api/perl
rm credentials.dat
```

For everything else,
[file an issue](https://github.com/googlegenomics/getting-started-with-the-api/issues/new)
if you run into problems and we'll do our best to help!
