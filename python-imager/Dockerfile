# Copyright 2023 Antaris, Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM quay.io/antaris-inc/satos-payload-app-python:stable

ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y python3-opencv
RUN python3 -m pip install --upgrade pip
RUN python3 -m pip install --upgrade opencv-python
RUN python3 -m pip install --upgrade numpy
RUN python3 -m pip install --upgrade rasterio cartopy pillow shapely

ADD samples /opt/antaris/app/samples
ADD src /opt/antaris/app/src
ADD entrypoint.sh /opt/antaris/app/entrypoint.sh

ENV PYTHONPATH=/opt/antaris/app/src
