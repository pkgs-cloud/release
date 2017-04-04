# pkgs.cloud – Release Repository

RPM packages for RHEL / CentOS 7

### Purpose

**pkgs.cloud** was created to simplify RPM package management on Red Hat Enterprise Linux and CentOS systems.

A single YUM repository gives access to a number of additional YUM repositories and thousands of RPM packages.

pkgs.cloud provides up-to-date versions of various RPM packages with the latest security patches.

The number of repositories and packages will continue to grow weekly.

### Installation

1. Install pkgs.cloud release repository package  

  ```bash
  yum install https://get.pkgs.cloud/release.rpm -y
  ```

2. View available repository packages  

  ```bash
  yum --disablerepo="*" --enablerepo="pkgs.cloud" list available
  ```

3. Install additional repository, eg:  

  ```bash
  yum install pkgs.cloud-nodejs-7.x-release -y
  ```  

  _short release package name can be used instead, prefix `pkgs.cloud-` is optional:_  

  ```bash
  yum install nodejs-7.x-release -y
  ```

4. See what's available under new repository or search for packages, eg:  

  ```bash
  yum --disablerepo="*" --enablerepo="pkgs.cloud-nodejs-7.x" list available
  yum search nodejs
  ```

5. Install required packages, eg:  
  
  ```bash
  yum install nodejs nodejs-devel -y
  ```
  
#### Repository 

Name of a repository is a name of its release package without `-release` suffix, eg:  

| Package                       | Repository            | Installation                     |
| ----------------------------- | --------------------- | -------------------------------- |
| pkgs.cloud-release            | pkgs.cloud            | _see above_                      |
| pkgs.cloud-nodejs-7.x-release | pkgs.cloud-nodejs-7.x | `yum install nodejs-7.x-release` |
| pkgs.cloud-php-7.1-release    | pkgs.cloud-php-7.1    | `yum install php-7.1-release`    |

Release packages can be referred by either its long name or a short one (without prefix), eg:

| Long Name                     | Short Name            | RPM Name                                       |
| ----------------------------- | --------------------- | ---------------------------------------------- |
| pkgs.cloud-nodejs-7.x-release | nodejs-7.x-release    | pkgs.cloud-nodejs-7.x-release-1.0-0.noarch.rpm |


```
yum install pkgs.cloud-nodejs-7.x-release
yum install nodejs-7.x-release
yum install pkgs.cloud-nodejs-7.x-release-1.0-0.noarch.rpm
```

### Removal

To remove **pkgs.cloud** repositories simply erase related release packages, eg:

```bash
yum erase pkgs.cloud-release
yum erase pkgs.cloud-nodejs-7.x-release

```

### Need help with RPM packages?

- [Open an issue](https://github.com/pkgs-cloud/release/issues)

---

##### DISCLAIMER

THIS SOFTWARE IS PROVIDED "AS IS" AND ANY EXPRESSED OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE REGENTS OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)
HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.