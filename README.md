# Helm and Kubernetes-cli legacy versions

Attempt to rebuild previous versions of clients needed for communication with existing older production infrastructure


## Update with new formula

When new version of Helm or Kubernetes-cli is released, brew will update its packages. To view all the previous versions of the tool, we can visit the brew histories of [Helm](https://github.com/Homebrew/homebrew-core/commits/7877b4bbcfa48028349a5cbed0d2f6ef5dbcc84b/Formula/helm.rb) and [Kubernetes-cli](https://github.com/Homebrew/homebrew-core/commits/674e098c3efce9196d91397d325c66d488aacc6b/Formula/kubernetes-cli.rb) to view list of all the previous versions.


### Updating tap
    
We can download the specific version of the formula from brew to the Tap using command,

***`brew extract helm <YOUR_GITHUB_USER>/<YOUR_TAP_REPOSITORY_NAME> --version=<required version>`***

``e.g: brew extract helm nintexplatform/versions --version=3.7.0``

This brew command will create specific version formula with name **`helm@3.7.0.rb`** in the local machine Tap.

***``Tap in local machine exists in: 
  /usr/local/Homebrew/Library/Taps/nintexplatform/homebrew-versions/Formula/<packages>``***
  
Once new formula is created, it should be pushed to remote [Nintexplatform public repository](https://github.com/nintexplatform/homebrew-versions).


:link: [Brew formula extract documentation](https://docs.brew.sh/Versions.html)


## Testing new formula

We can test the new formula created by using brew command,

`brew install --build-from-source ./helm@3.7.0.rb`

## How do I install these formulae?

`brew install nintexplatform/versions/<formula>`

`e.g brew install nintexplatform/versions/helm@3.7.0`

Or 

`brew tap nintexplatform/versions` and

then `brew install <formula>` e.g `brew install helm@3.7.0`.