---
weight: 1
bookFlatSection: true
title: "The API"
---

# API Docs

This API is still a work in progress so expect to see changes, hopefully non-breaking unless they're necessary. The underlying data shouldn't be affected though.

## Registration

    curl -H "Content-Type: application/json" -X POST \
        -d '{"username": "your-username", "email" : "your-email", \
        "password" : "your-password"}' \
        "http://jsonify.me/register"

## Authentication

    curl -H "Content-Type: application/json" -X POST \
        -d '{"username": "your-username", "email" : "your-email", \
        "password" : "your-password"}' \
        "http://jsonify.me/auth"

## Setting your subdomain

    curl -H "Content-Type: application/json" \
        -H "Authorization: Bearer token-from-auth-call" \
        -X POST -d '{"username": "your-username", \
        "subdomain" : "sub-domain-you-want-to-use" }' \
        "http://jsonify.me/update"

## Setting your info

    curl -H "Content-Type: application/json" \
        -H "Authorization: Bearer token-from-auth-call" \
        -X POST -d 'json_object' "http://your-sub-domain/"

    curl -H "Content-Type: application/json" \
        -H "Authorization: Bearer token-from-auth-call" \
        -X POST -d 'json_object' "http://username.jsonify.me/"

## Getting your info

    curl -L -H "Content-Type: application/json" \
        -X GET "http://your-sub-domain"

    curl -L -H "Content-Type: application/json" \
        -X GET "http://username.jsonify.me/"
