# Copyright 2019 HTCondor Team, Computer Sciences Department,
# University of Wisconsin-Madison, WI.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM continuumio/anaconda3:2019.07
ENV PATH=/opt/conda/bin/:${PATH}

LABEL maintainer="karpel@wisc.edu"

COPY . /tmp/htmap
RUN python3 -m pip install --no-cache-dir /tmp/htmap/ \
 && rm -rf /tmp/htmap

COPY htmap-exec/singularity.d /.singularity.d

ARG USER=htmap
RUN groupadd ${USER} \
 && useradd -m -g ${USER} ${USER}
USER ${USER}
