let _self = this
      _self.axiosInstance.get('/repos/' + _self.repositoryOwner + '/' + _self.repositoryName + '/branches').then(function (result) {
        result.data.forEach(function (each) {
          _self.branches.push({text: each.name, sha: each.commit.sha})
        })
      })
      _self.axiosInstance.get(`/repos/${_self.repositoryOwner}/${_self.repositoryName}/contents/${_self.path}`).then(function (response) {
        console.log(response)
        _self.blobSha = response.data.sha
        _self.code = decodeURIComponent(atob(response.data.content).split('').map(function (c) {
          return '%' + ('00' + c.charCodeAt(0).toString(16)).slice(-2)
        }).join(''))
      })