#
# This file is part of the BlizzLikeCore Project. See CREDITS and LICENSE files
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA
#

if(CMAKE_COMPILER_IS_GNUCXX)
  add_definitions(--no-warnings)
elseif(MSVC)
  add_definitions(/W0)
endif()

if(NOT ACE_USE_EXTERNAL)
  add_subdirectory(ACE_wrappers)
endif()

add_subdirectory(recastnavigation)
add_subdirectory(src)

if(TOOLS)
  add_subdirectory(libmpq)
endif()
