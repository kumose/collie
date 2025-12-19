#
# Copyright 2024 The Kumo Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

find_package(Boost 1.54.0 REQUIRED COMPONENTS unit_test_framework)

kmcmake_cc_test(
        NAME trie_test
        MODULE tsl
        SOURCES
            trie_main.cc
            trie_map_tests.cc
            trie_set_tests.cc
        CXXOPTS
        -fno-permissive
        LINKS
            Boost::unit_test_framework
            ${KMCMAKE_DEPS_LINK}
)

kmcmake_cc_test(
        NAME robin_test
        MODULE tsl
        SOURCES
        robin_main.cc
        robin_map_tests.cc
        robin_set_tests.cc
        LINKS
        Boost::unit_test_framework
        ${KMCMAKE_DEPS_LINK}
)

kmcmake_cc_test(
        NAME hopscotch_test
        MODULE tsl
        SOURCES
        hopscotch_main.cc
        hopscotch_map_tests.cc
        hopscotch_set_tests.cc
        hopscotch_custom_allocator_tests.cc
        hopscotch_policy_tests.cc
        LINKS
        Boost::unit_test_framework
        ${KMCMAKE_DEPS_LINK}
)

kmcmake_cc_test(
        NAME sparse_test
        MODULE tsl
        SOURCES
        sparse_main.cc
        sparse_custom_allocator_tests.cc
        sparse_map_tests.cc
        sparse_policy_tests.cc
        sparse_popcount_tests.cc
        sparse_set_tests.cc
        LINKS
        Boost::unit_test_framework
        ${KMCMAKE_DEPS_LINK}
)

kmcmake_cc_test(
        NAME ordered_test
        MODULE tsl
        SOURCES
        ordered_main.cc
        ordered_map_tests.cc
        ordered_set_tests.cc
        ordered_custom_allocator_tests.cc
        LINKS
        Boost::unit_test_framework
        ${KMCMAKE_DEPS_LINK}
)


kmcmake_cc_binary(
        NAME robin_test
        NAMESPACE tsl
        SOURCES
        hopscotch_ex.cc
        LINKS
        ${KMCMAKE_DEPS_LINK}
)